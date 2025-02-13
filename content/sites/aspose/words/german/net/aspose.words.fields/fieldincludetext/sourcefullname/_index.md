---
title: FieldIncludeText.SourceFullName
second_title: Aspose.Words für .NET-API-Referenz
description: FieldIncludeText eigendom. Ruft den Speicherort des Dokuments mithilfe eines IRI ab oder legt ihn fest.
type: docs
weight: 70
url: /de/net/aspose.words.fields/fieldincludetext/sourcefullname/
---
## FieldIncludeText.SourceFullName property

Ruft den Speicherort des Dokuments mithilfe eines IRI ab oder legt ihn fest.

```csharp
public string SourceFullName { get; set; }
```

### Beispiele

Zeigt, wie ein INCLUDETEXT-Feld erstellt und seine Eigenschaften festgelegt werden.

```csharp
public void FieldIncludeText()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Im Folgenden finden Sie zwei Möglichkeiten, INCLUDETEXT-Felder zu verwenden, um den Inhalt einer XML-Datei im lokalen Dateisystem anzuzeigen.
    // 1 - Führen Sie eine XSL-Transformation für ein XML-Dokument durch:
    FieldIncludeText fieldIncludeText = CreateFieldIncludeText(builder, MyDir + "CD collection data.xml", false, "text/xml", "XML", "ISO-8859-1");
    fieldIncludeText.XslTransformation = MyDir + "CD collection XSL transformation.xsl";

    builder.Writeln();

    // 2 - Verwenden Sie einen XPath, um bestimmte Elemente aus einem XML-Dokument zu entnehmen:
    fieldIncludeText = CreateFieldIncludeText(builder, MyDir + "CD collection data.xml", false, "text/xml", "XML", "ISO-8859-1");
    fieldIncludeText.NamespaceMappings = "xmlns:n='myNamespace'";
    fieldIncludeText.XPath = "/catalog/cd/title";

    doc.Save(ArtifactsDir + "Field.INCLUDETEXT.docx");

/// <summary>
/// Verwenden Sie einen Document Builder, um ein INCLUDETEXT-Feld mit benutzerdefinierten Eigenschaften einzufügen.
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

### Siehe auch

* class [FieldIncludeText](../)
* namensraum [Aspose.Words.Fields](../../fieldincludetext/)
* Montage [Aspose.Words](../../../)


