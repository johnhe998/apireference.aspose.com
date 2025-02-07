---
title: ImportFormatOptions.KeepSourceNumbering
second_title: Aspose.Words för .NET API Referens
description: ImportFormatOptions fast egendom. Hämtar eller ställer in ett booleskt värde som anger hur numreringen kommer att importeras när den krockar i käll och destinationsdokument. Standardvärdet ärfalsk .
type: docs
weight: 50
url: /sv/net/aspose.words/importformatoptions/keepsourcenumbering/
---
## ImportFormatOptions.KeepSourceNumbering property

Hämtar eller ställer in ett booleskt värde som anger hur numreringen kommer att importeras när den krockar i käll- och destinationsdokument. Standardvärdet är`falsk` .

```csharp
public bool KeepSourceNumbering { get; set; }
```

### Exempel

Visar hur man löser en konflikt när man importerar dokument som har listor med samma listdefinitionsidentifierare.

```csharp
Document srcDoc = new Document(MyDir + "List with the same definition identifier - source.docx");
Document dstDoc = new Document(MyDir + "List with the same definition identifier - destination.docx");

// Ställ in egenskapen "KeepSourceNumbering" till "true" för att tillämpa ett annat listdefinitions-ID
// till identiska stilar som Aspose.Words importerar dem till måldokument.
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };

dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, importFormatOptions);
dstDoc.UpdateListLabels();
```

Visar hur man importerar ett dokument med numrerade listor.

```csharp
Document srcDoc = new Document(MyDir + "List source.docx");
Document dstDoc = new Document(MyDir + "List destination.docx");

Assert.AreEqual(4, dstDoc.Lists.Count);

ImportFormatOptions options = new ImportFormatOptions();

// Om det finns en konflikt mellan liststilar, använd listformatet för källdokumentet.
// Ställ in egenskapen "KeepSourceNumbering" till "false" för att inte importera några listnummer till måldokumentet.
// Ställ in "KeepSourceNumbering"-egenskapen till "true" importera all clashing
// liststilsnumrering med samma utseende som den hade i källdokumentet.
options.KeepSourceNumbering = isKeepSourceNumbering;

dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);
dstDoc.UpdateListLabels();

Assert.AreEqual(isKeepSourceNumbering ? 5 : 4, dstDoc.Lists.Count);
```

Visar hur man löser listnumreringskrockar i käll- och måldokument.

```csharp
// Öppna ett dokument med ett anpassat listnumreringsschema och klona det sedan.
// Eftersom båda har samma numreringsformat kommer formaten att krocka om vi importerar ett dokument till det andra.
Document srcDoc = new Document(MyDir + "Custom list numbering.docx");
Document dstDoc = srcDoc.Clone();

// När vi importerar dokumentets klon till originalet och sedan lägger till det,
// då kommer de två listorna med samma listformat att förenas.
// Om vi ställer in "KeepSourceNumbering"-flaggan till "false", kommer listan från dokumentklonen
// som vi lägger till originalet kommer att fortsätta numreringen av listan vi lägger till den.
// Detta kommer effektivt att slå samman de två listorna till en.
// Om vi ställer in "KeepSourceNumbering"-flaggan till "true", kommer dokumentklonen
// list kommer att bevara sin ursprungliga numrering, vilket gör att de två listorna visas som separata listor. 
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.KeepSourceNumbering = keepSourceNumbering;

NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepDifferentStyles, importFormatOptions);
foreach (Paragraph paragraph in srcDoc.FirstSection.Body.Paragraphs)
{
    Node importedNode = importer.ImportNode(paragraph, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}

dstDoc.UpdateListLabels();

if (keepSourceNumbering)
{
    Assert.AreEqual(
        "6. Item 1\r\n" +
        "7. Item 2 \r\n" +
        "8. Item 3\r\n" +
        "9. Item 4\r\n" +
        "6. Item 1\r\n" +
        "7. Item 2 \r\n" +
        "8. Item 3\r\n" +
        "9. Item 4", dstDoc.FirstSection.Body.ToString(SaveFormat.Text).Trim());
}
else
{
    Assert.AreEqual(
        "6. Item 1\r\n" +
        "7. Item 2 \r\n" +
        "8. Item 3\r\n" +
        "9. Item 4\r\n" +
        "10. Item 1\r\n" +
        "11. Item 2 \r\n" +
        "12. Item 3\r\n" +
        "13. Item 4", dstDoc.FirstSection.Body.ToString(SaveFormat.Text).Trim());
}
```

### Se även

* class [ImportFormatOptions](../)
* namnutrymme [Aspose.Words](../../importformatoptions/)
* hopsättning [Aspose.Words](../../../)


