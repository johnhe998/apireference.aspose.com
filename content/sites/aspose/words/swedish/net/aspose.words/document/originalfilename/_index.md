---
title: Document.OriginalFileName
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Hämtar originalfilnamnet för dokumentet.
type: docs
weight: 270
url: /sv/net/aspose.words/document/originalfilename/
---
## Document.OriginalFileName property

Hämtar originalfilnamnet för dokumentet.

```csharp
public string OriginalFileName { get; }
```

### Anmärkningar

Returnerar null om dokumentet laddades från en ström eller skapades tomt.

### Exempel

Visar hur man hämtar information om ett dokuments laddningsoperation.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(MyDir + "Document.docx", doc.OriginalFileName);
Assert.AreEqual(LoadFormat.Docx, doc.OriginalLoadFormat);
```

Visar hur du använder FileFormatUtil-metoderna för att upptäcka formatet på ett dokument.

```csharp
// Ladda ett dokument från en fil som saknar filtillägg, och identifiera sedan dess filformat.
using (FileStream docStream = File.OpenRead(MyDir + "Word document with missing file extension"))
{
    FileFormatInfo info = FileFormatUtil.DetectFileFormat(docStream);
    LoadFormat loadFormat = info.LoadFormat;

    Assert.AreEqual(LoadFormat.Doc, loadFormat);

    // Nedan finns två metoder för att konvertera ett LoadFormat till dess motsvarande SaveFormat.
    // 1 - Hämta filtilläggssträngen för LoadFormat och hämta sedan motsvarande SaveFormat från den strängen:
    string fileExtension = FileFormatUtil.LoadFormatToExtension(loadFormat);
    SaveFormat saveFormat = FileFormatUtil.ExtensionToSaveFormat(fileExtension);

    // 2 - Konvertera LoadFormat direkt till dess SaveFormat:
    saveFormat = FileFormatUtil.LoadFormatToSaveFormat(loadFormat);

    // Ladda ett dokument från strömmen och spara det sedan i det automatiskt upptäckta filtillägget.
    Document doc = new Document(docStream);

    Assert.AreEqual(".doc", FileFormatUtil.SaveFormatToExtension(saveFormat));

    doc.Save(ArtifactsDir + "File.SaveToDetectedFileFormat" + FileFormatUtil.SaveFormatToExtension(saveFormat));
}
```

### Se även

* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


