---
title: FieldStyleRef.SuppressNonDelimiters
second_title: Aspose.Words für .NET-API-Referenz
description: FieldStyleRef eigendom. Ruft ab oder legt fest ob NichtTrennzeichen unterdrückt werden sollen.
type: docs
weight: 80
url: /de/net/aspose.words.fields/fieldstyleref/suppressnondelimiters/
---
## FieldStyleRef.SuppressNonDelimiters property

Ruft ab oder legt fest, ob Nicht-Trennzeichen unterdrückt werden sollen.

```csharp
public bool SuppressNonDelimiters { get; set; }
```

### Beispiele

Zeigt, wie STYLEREF-Felder verwendet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine Liste basierend auf einer Microsoft Word-Listenvorlage.
Aspose.Words.Lists.List list = doc.Lists.Add(Aspose.Words.Lists.ListTemplate.NumberDefault);

// Diese generierte Liste zeigt "1.a )" an.
 // Das Leerzeichen vor der Klammer ist kein Trennzeichen, das wir unterdrücken können.
list.ListLevels[0].NumberFormat = "\x0000.";
list.ListLevels[1].NumberFormat = "\x0001 )";

// Text hinzufügen und Absatzstile anwenden, auf die STYLEREF-Felder verweisen.
builder.ListFormat.List = list;
builder.ListFormat.ListIndent();
builder.ParagraphFormat.Style = doc.Styles["List Paragraph"];
builder.Writeln("Item 1");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln("Item 2");
builder.ParagraphFormat.Style = doc.Styles["List Paragraph"];
builder.Writeln("Item 3");
builder.ListFormat.RemoveNumbers();
builder.ParagraphFormat.Style = doc.Styles["Normal"];

// Platziere ein STYLEREF-Feld in der Kopfzeile und zeige den ersten Text im "Listenabsatz"-Stil im Dokument an.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
FieldStyleRef field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "List Paragraph";

// Platziere ein STYLEREF-Feld in der Fußzeile und lasse es den letzten Text anzeigen.
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "List Paragraph";
field.SearchFromBottom = true;

builder.MoveToDocumentEnd();

// Wir können auch STYLEREF-Felder verwenden, um auf die Listennummern von Listen zu verweisen.
builder.Write("\nParagraph number: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumber = true;

builder.Write("\nParagraph number, relative context: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInRelativeContext = true;

builder.Write("\nParagraph number, full context: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInFullContext = true;

builder.Write("\nParagraph number, full context, non-delimiter chars suppressed: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInFullContext = true;
field.SuppressNonDelimiters = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.STYLEREF.docx");
```

### Siehe auch

* class [FieldStyleRef](../)
* namensraum [Aspose.Words.Fields](../../fieldstyleref/)
* Montage [Aspose.Words](../../../)


