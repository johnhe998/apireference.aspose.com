---
title: ImportFormatOptions.IgnoreTextBoxes
second_title: Aspose.Words för .NET API Referens
description: ImportFormatOptions fast egendom. Hämtar eller ställer in ett booleskt värde som anger att källformatering av textrutor innehåll ignored omKeepSourceFormatting läge används. Standardvärdet ärSann .
type: docs
weight: 40
url: /sv/net/aspose.words/importformatoptions/ignoretextboxes/
---
## ImportFormatOptions.IgnoreTextBoxes property

Hämtar eller ställer in ett booleskt värde som anger att källformatering av textrutor innehåll ignored omKeepSourceFormatting läge används. Standardvärdet är`Sann` .

```csharp
public bool IgnoreTextBoxes { get; set; }
```

### Exempel

Visar hur du hanterar textruteformatering medan du lägger till ett dokument.

```csharp
// Skapa ett dokument som kommer att ha noder från ett annat dokument infogat i det.
Document dstDoc = new Document();
DocumentBuilder builder = new DocumentBuilder(dstDoc);

builder.Writeln("Hello world!");

// Skapa ett annat dokument med en textruta, som vi importerar till det första dokumentet.
Document srcDoc = new Document();
builder = new DocumentBuilder(srcDoc);

Shape textBox = builder.InsertShape(ShapeType.TextBox, 300, 100);
builder.MoveTo(textBox.FirstParagraph);
builder.ParagraphFormat.Style.Font.Name = "Courier New";
builder.ParagraphFormat.Style.Font.Size = 24;
builder.Write("Textbox contents");

// Ställ in en flagga för att ange om textruteformateringen ska raderas eller bevaras
// medan du importerar dem till andra dokument.
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.IgnoreTextBoxes = ignoreTextBoxes;

// Importera textrutan från källdokumentet till måldokumentet,
// och verifiera sedan om vi har bevarat stilen på dess textinnehåll.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
Shape importedTextBox = (Shape)importer.ImportNode(textBox, true);
dstDoc.FirstSection.Body.Paragraphs[1].AppendChild(importedTextBox);

if (ignoreTextBoxes)
{
    Assert.AreEqual(12.0d, importedTextBox.FirstParagraph.Runs[0].Font.Size);
    Assert.AreEqual("Times New Roman", importedTextBox.FirstParagraph.Runs[0].Font.Name);
}
else
{
    Assert.AreEqual(24.0d, importedTextBox.FirstParagraph.Runs[0].Font.Size);
    Assert.AreEqual("Courier New", importedTextBox.FirstParagraph.Runs[0].Font.Name);
}

dstDoc.Save(ArtifactsDir + "DocumentBuilder.IgnoreTextBoxes.docx");
```

### Se även

* class [ImportFormatOptions](../)
* namnutrymme [Aspose.Words](../../importformatoptions/)
* hopsättning [Aspose.Words](../../../)


