---
title: FieldNextIf.LeftExpression
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldNextIf propriété. Obtient ou définit la partie gauche de lexpression de comparaison.
type: docs
weight: 30
url: /fr/net/aspose.words.fields/fieldnextif/leftexpression/
---
## FieldNextIf.LeftExpression property

Obtient ou définit la partie gauche de l'expression de comparaison.

```csharp
public string LeftExpression { get; set; }
```

### Exemples

Montre comment utiliser les champs NEXT/NEXTIF pour fusionner plusieurs lignes en une seule page lors d'un publipostage.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Crée une source de données pour notre publipostage avec 3 lignes.
    // Un publipostage qui utilise ce tableau créerait normalement un document de 3 pages.
    DataTable table = new DataTable("Employees");
    table.Columns.Add("Courtesy Title");
    table.Columns.Add("First Name");
    table.Columns.Add("Last Name");
    table.Rows.Add("Mr.", "John", "Doe");
    table.Rows.Add("Mrs.", "Jane", "Cardholder");
    table.Rows.Add("Mr.", "Joe", "Bloggs");

    InsertMergeFields(builder, "First row: ");

    // Si nous avons plusieurs champs de fusion avec le même FieldName,
    // ils recevront les données de la même ligne de la source de données et afficheront la même valeur après la fusion.
    // Un champ NEXT indique instantanément au publipostage de descendre d'une ligne,
    // ce qui signifie que tous les champs MERGEFIELD qui suivent le champ NEXT recevront les données de la ligne suivante.
    // Assurez-vous de ne jamais essayer de passer à la ligne suivante alors que vous êtes déjà sur la dernière ligne.
    FieldNext fieldNext = (FieldNext)builder.InsertField(FieldType.FieldNext, true);

    Assert.AreEqual(" NEXT ", fieldNext.GetFieldCode());

    // Après la fusion, les valeurs de source de données que ces MERGEFIELD acceptent
     // se retrouvera sur la même page que les CHAMPS DE FUSION ci-dessus.
    InsertMergeFields(builder, "Second row: ");

    // Un champ NEXTIF a la même fonction qu'un champ NEXT,
    // mais il passe à la ligne suivante uniquement si une déclaration construite par les 3 propriétés suivantes est vraie.
    FieldNextIf fieldNextIf = (FieldNextIf)builder.InsertField(FieldType.FieldNextIf, true);
    fieldNextIf.LeftExpression = "5";
    fieldNextIf.RightExpression = "2 + 3";
    fieldNextIf.ComparisonOperator = "=";

    Assert.AreEqual(" NEXTIF  5 = \"2 + 3\"", fieldNextIf.GetFieldCode());

    // Si la comparaison affirmée par le champ ci-dessus est correcte,
    // les 3 champs de fusion suivants prendront les données de la troisième ligne.
    // Sinon, ces champs reprendront les données de la ligne 2.
    InsertMergeFields(builder, "Third row: ");

    doc.MailMerge.Execute(table);

     // Notre source de données a 3 lignes et nous avons sauté des lignes deux fois.
    // Notre document de sortie aura 1 page avec les données des 3 lignes.
    doc.Save(ArtifactsDir + "Field.NEXT.NEXTIF.docx");

/// <summary>
/// Utilise un générateur de document pour insérer des MERGEFIELD pour une source de données qui contient des colonnes nommées "Courtesy Title", "First Name" et "Last Name".
/// </summary>
public void InsertMergeFields(DocumentBuilder builder, string firstFieldTextBefore)
{
    InsertMergeField(builder, "Courtesy Title", firstFieldTextBefore, " ");
    InsertMergeField(builder, "First Name", null, " ");
    InsertMergeField(builder, "Last Name", null, null);
    builder.InsertParagraph();
}

/// <summary>
/// Utilise un générateur de document pour insérer un MERRGEFIELD avec les propriétés spécifiées.
/// </summary>
public void InsertMergeField(DocumentBuilder builder, string fieldName, string textBefore, string textAfter)
{
    FieldMergeField field = (FieldMergeField) builder.InsertField(FieldType.FieldMergeField, true);
    field.FieldName = fieldName;
    field.TextBefore = textBefore;
    field.TextAfter = textAfter;
}
```

### Voir également

* class [FieldNextIf](../)
* espace de noms [Aspose.Words.Fields](../../fieldnextif/)
* Assemblée [Aspose.Words](../../../)


