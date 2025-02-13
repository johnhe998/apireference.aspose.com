---
title: MailMerge.UseNonMergeFields
second_title: Référence de l'API Aspose.Words pour .NET
description: MailMerge propriété. Lorsquil est vrai spécifie quen plus des champs MERGEFIELD le publipostage est effectué dans dautres types de champs et également dans les balises fieldName.
type: docs
weight: 150
url: /fr/net/aspose.words.mailmerging/mailmerge/usenonmergefields/
---
## MailMerge.UseNonMergeFields property

Lorsqu'il est vrai, spécifie qu'en plus des champs MERGEFIELD, le publipostage est effectué dans d'autres types de champs et également dans les balises "{{fieldName}}".

```csharp
public bool UseNonMergeFields { get; set; }
```

### Remarques

Normalement, le publipostage n'est effectué que dans les champs MERGEFIELD, mais plusieurs clients ont créé leur reporting à l'aide d'autres champs et ont créé de nombreux documents de cette manière. Pour simplifier la migration (et parce que cette approche était utilisée indépendamment par plusieurs clients), la possibilité de fusionner dans d'autres champs a été introduite.

Lorsque **UseNonMergeFields** est défini sur true, Aspose.Words effectuera un publipostage dans les champs suivants :

MERGEFIELD FieldName

MACROBUTTON NOMACRO NomChamp

SI 0 = 0 "{NomChamp}" ""

Aussi, quand **UserNonMergeFieldsUserNonMergeFields** est défini sur true, Aspose.Words effectuera un publipostage dans les balises de texte "{{fieldName}}". Ce ne sont pas des champs, mais juste des balises de texte.

### Exemples

Montre comment conserver l'apparence d'autres balises de publipostage qui ne sont pas utilisées lors d'un publipostage.

```csharp
public void PreserveUnusedTags(bool preserveUnusedTags)
{
    Document doc = CreateSourceDocWithAlternativeMergeFields();
    DataTable dataTable = CreateSourceTablePreserveUnusedTags();

    // Par défaut, un publipostage place les données de chaque ligne d'une table dans des MERGEFIELD, qui nomment les colonnes de cette table. 
    // Notre document n'a pas de tels champs, mais il a des balises de texte en clair entourées d'accolades.
    // Si nous définissons le drapeau "PreserveUnusedTags" sur "true", nous pourrions traiter ces balises comme des MERGEFIELDs
    // pour permettre à notre publipostage d'insérer des données de la source de données à ces balises.
    // Si nous définissons le drapeau "PreserveUnusedTags" sur "false",
    // le publipostage convertira ces balises en MERGEFIELD et les laissera vides.
    doc.MailMerge.PreserveUnusedTags = preserveUnusedTags;
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.PreserveUnusedTags.docx");

    // Notre document a une balise pour une colonne nommée "Column2", qui n'existe pas dans la table.
    // Si nous définissons le drapeau "PreserveUnusedTags" sur "false", then the mail merge will convert this tag into a MERGEFIELD.
    Assert.AreEqual(doc.GetText().Contains("{{ Column2 }}"), preserveUnusedTags);

    if (preserveUnusedTags)
        Assert.AreEqual(0, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
    else
        Assert.AreEqual(1, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
}

/// <summary>
/// Créez un document et ajoutez deux balises de texte en clair pouvant agir comme MERGEFIELD lors d'un publipostage.
/// </summary>
private static Document CreateSourceDocWithAlternativeMergeFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("{{ Column1 }}");
    builder.Writeln("{{ Column2 }}");

    // Nos balises seront enregistrées en tant que destinations pour les données de publipostage uniquement si nous définissons ceci sur true.
    doc.MailMerge.UseNonMergeFields = true;

    return doc;
}

/// <summary>
/// Créez un tableau de données simple avec une colonne.
/// </summary>
private static DataTable CreateSourceTablePreserveUnusedTags()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Rows.Add(new object[] { "Value1" });

    return dataTable;
}
```

### Voir également

* class [MailMerge](../)
* espace de noms [Aspose.Words.MailMerging](../../mailmerge/)
* Assemblée [Aspose.Words](../../../)


