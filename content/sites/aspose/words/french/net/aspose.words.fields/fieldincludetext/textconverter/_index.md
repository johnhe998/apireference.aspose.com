---
title: FieldIncludeText.TextConverter
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldIncludeText propriété. Obtient ou définit le nom du convertisseur de texte pour le format du fichier inclus.
type: docs
weight: 80
url: /fr/net/aspose.words.fields/fieldincludetext/textconverter/
---
## FieldIncludeText.TextConverter property

Obtient ou définit le nom du convertisseur de texte pour le format du fichier inclus.

```csharp
public string TextConverter { get; set; }
```

### Exemples

Montre comment créer un champ INCLUDETEXT et définir ses propriétés.

```csharp
public void FieldIncludeText()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Vous trouverez ci-dessous deux manières d'utiliser les champs INCLUDETEXT pour afficher le contenu d'un fichier XML dans le système de fichiers local.
    // 1 - Effectuez une transformation XSL sur un document XML :
    FieldIncludeText fieldIncludeText = CreateFieldIncludeText(builder, MyDir + "CD collection data.xml", false, "text/xml", "XML", "ISO-8859-1");
    fieldIncludeText.XslTransformation = MyDir + "CD collection XSL transformation.xsl";

    builder.Writeln();

    // 2 - Utilisez un XPath pour prendre des éléments spécifiques d'un document XML :
    fieldIncludeText = CreateFieldIncludeText(builder, MyDir + "CD collection data.xml", false, "text/xml", "XML", "ISO-8859-1");
    fieldIncludeText.NamespaceMappings = "xmlns:n='myNamespace'";
    fieldIncludeText.XPath = "/catalog/cd/title";

    doc.Save(ArtifactsDir + "Field.INCLUDETEXT.docx");

/// <summary>
/// Utilisez un générateur de document pour insérer un champ INCLUDETEXT avec des propriétés personnalisées.
/// </summary>
public FieldIncludeText CreateFieldIncludeText(DocumentBuilder builder, string sourceFullName, bool lockFields, string mimeType, string textConverter, string encoding)
{
    FieldIncludeText fieldIncludeText = (FieldIncludeText)builder.InsertField(FieldType.FieldIncludeText, true);
    fieldIncludeText.SourceFullName = sourceFullName;
    fieldIncludeText.LockFields = lockFields;
    fieldIncludeText.MimeType = mimeType;
    fieldIncludeText.TextConverter = textConverter;
    fieldIncludeText.Encoding = encoding;

    return fieldIncludeText;
}
```

### Voir également

* class [FieldIncludeText](../)
* espace de noms [Aspose.Words.Fields](../../fieldincludetext/)
* Assemblée [Aspose.Words](../../../)


