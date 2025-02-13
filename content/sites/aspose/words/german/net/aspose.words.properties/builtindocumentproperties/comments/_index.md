---
title: BuiltInDocumentProperties.Comments
second_title: Aspose.Words für .NET-API-Referenz
description: BuiltInDocumentProperties eigendom. Ruft die Dokumentkommentare ab oder legt sie fest.
type: docs
weight: 60
url: /de/net/aspose.words.properties/builtindocumentproperties/comments/
---
## BuiltInDocumentProperties.Comments property

Ruft die Dokumentkommentare ab oder legt sie fest.

```csharp
public string Comments { get; set; }
```

### Beispiele

Zeigt, wie Sie mit integrierten Dokumenteigenschaften in der Kategorie "Beschreibung" arbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

// Unten sind vier eingebaute Dokumenteigenschaften, die Felder haben, die ihre Werte im Dokumentkörper anzeigen können.
// 1 - "Autor"-Eigenschaft, die wir mit einem AUTHOR-Feld anzeigen können:
properties.Author = "John Doe";
builder.Write("Author:\t");
builder.InsertField(FieldType.FieldAuthor, true);

// 2 - "Title"-Eigenschaft, die wir mit einem TITLE-Feld anzeigen können:
properties.Title = "John's Document";
builder.Write("\nDoc title:\t");
builder.InsertField(FieldType.FieldTitle, true);

// 3 - "Subject"-Eigenschaft, die wir mit einem SUBJECT-Feld anzeigen können:
properties.Subject = "My subject";
builder.Write("\nSubject:\t");
builder.InsertField(FieldType.FieldSubject, true);

// 4 - "Comments"-Eigenschaft, die wir mit einem COMMENTS-Feld anzeigen können:
properties.Comments = $"This is {properties.Author}'s document about {properties.Subject}";
builder.Write("\nComments:\t\"");
builder.InsertField(FieldType.FieldComments, true);
builder.Write("\"");

// Die eingebaute Eigenschaft "Kategorie" hat kein Feld, das ihren Wert anzeigen kann.
properties.Category = "My category";

// Wir können mehrere Schlüsselwörter für ein Dokument festlegen, indem wir den Zeichenfolgenwert der Eigenschaft "Schlüsselwörter" durch Semikolons trennen.
properties.Keywords = "Tag 1; Tag 2; Tag 3";

// Wir können im Windows Explorer mit der rechten Maustaste auf dieses Dokument klicken und diese Eigenschaften unter "Eigenschaften" finden -> "Einzelheiten".
// Die eingebaute Eigenschaft „Autor“ befindet sich in der Gruppe „Ursprung“ und die anderen in der Gruppe „Beschreibung“.
doc.Save(ArtifactsDir + "DocumentProperties.Description.docx");
```

### Siehe auch

* class [BuiltInDocumentProperties](../)
* namensraum [Aspose.Words.Properties](../../builtindocumentproperties/)
* Montage [Aspose.Words](../../../)


