---
title: ParagraphFormat.StyleIdentifier
second_title: Aspose.Words för .NET API Referens
description: ParagraphFormat fast egendom. Hämtar eller ställer in den språkoberoende stilidentifieraren för styckeformatet som tillämpas på denna formatering.
type: docs
weight: 340
url: /sv/net/aspose.words/paragraphformat/styleidentifier/
---
## ParagraphFormat.StyleIdentifier property

Hämtar eller ställer in den språkoberoende stilidentifieraren för styckeformatet som tillämpas på denna formatering.

```csharp
public StyleIdentifier StyleIdentifier { get; set; }
```

### Exempel

Visar hur man infogar en innehållsförteckning (TOC) i ett dokument med rubrikstilar som poster.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en innehållsförteckning för dokumentets första sida.
// Konfigurera tabellen för att ta upp stycken med rubriker på nivå 1 till 3.
// Ställ också in dess poster att vara hyperlänkar som tar oss
// till platsen för rubriken när du vänsterklickar i Microsoft Word.
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// Fyll i innehållsförteckningen genom att lägga till stycken med rubrikstilar.
// Varje sådan rubrik med en nivå mellan 1 och 3 kommer att skapa en post i tabellen.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;
builder.Writeln("Heading 3.1.3.1");
builder.Writeln("Heading 3.1.3.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");

// En innehållsförteckning är ett fält av en typ som behöver uppdateras för att visa ett aktuellt resultat.
doc.UpdateFields();
doc.Save(ArtifactsDir + "DocumentBuilder.InsertToc.docx");
```

### Se även

* enum [StyleIdentifier](../../styleidentifier/)
* class [ParagraphFormat](../)
* namnutrymme [Aspose.Words](../../paragraphformat/)
* hopsättning [Aspose.Words](../../../)


