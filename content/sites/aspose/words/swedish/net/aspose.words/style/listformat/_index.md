---
title: Style.ListFormat
second_title: Aspose.Words för .NET API Referens
description: Style fast egendom. Ger tillgång till listformateringsegenskaperna för en styckestil.
type: docs
weight: 100
url: /sv/net/aspose.words/style/listformat/
---
## Style.ListFormat property

Ger tillgång till listformateringsegenskaperna för en styckestil.

```csharp
public ListFormat ListFormat { get; }
```

### Anmärkningar

Den här egenskapen är endast giltig för styckestilar. För andra stiltyper returnerar den här egenskapen null.

### Exempel

Visar hur du skapar och använder ett styckeformat med listformatering.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en anpassad styckestil.
Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle1");
style.Font.Size = 24;
style.Font.Name = "Verdana";
style.ParagraphFormat.SpaceAfter = 12;

// Skapa en lista och se till att styckena som använder den här stilen kommer att använda den här listan.
style.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDefault);
style.ListFormat.ListLevelNumber = 0;

// Använd styckeformatet på dokumentbyggarens nuvarande stycke och lägg sedan till lite text.
builder.ParagraphFormat.Style = style;
builder.Writeln("Hello World: MyStyle1, bulleted list.");

// Ändra dokumentbyggarens stil till en som inte har någon listformatering och skriv ett stycke till.
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln("Hello World: Normal.");

builder.Document.Save(ArtifactsDir + "Styles.ParagraphStyleBulletedList.docx");
```

### Se även

* class [ListFormat](../../../aspose.words.lists/listformat/)
* class [Style](../)
* namnutrymme [Aspose.Words](../../style/)
* hopsättning [Aspose.Words](../../../)


