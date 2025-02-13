---
title: LoadOptions.MswVersion
second_title: Aspose.Words för .NET API Referens
description: LoadOptions fast egendom. Tillåter att ange att dokumentladdningsprocessen ska matcha en specifik MS Wordversion. Standardvärdet ärWord2019
type: docs
weight: 100
url: /sv/net/aspose.words.loading/loadoptions/mswversion/
---
## LoadOptions.MswVersion property

Tillåter att ange att dokumentladdningsprocessen ska matcha en specifik MS Word-version. Standardvärdet ärWord2019

```csharp
public MsWordVersion MswVersion { get; set; }
```

### Anmärkningar

Olika Word-versioner kan hantera vissa aspekter av dokumentinnehåll och formatering något annorlunda under laddningsprocessen, vilket kan resultera i mindre skillnader i dokumentobjektmodellen.

### Exempel

Visar hur man emulerar laddningsproceduren för en specifik Microsoft Word-version under dokumentladdning.

```csharp
// Som standard laddar Aspose.Words dokument enligt Microsoft Word 2019-specifikationen.
LoadOptions loadOptions = new LoadOptions();

Assert.AreEqual(MsWordVersion.Word2019, loadOptions.MswVersion);

// Det här dokumentet saknar standardformateringsstilen för stycken.
// Denna standardstil kommer att återskapas när vi laddar dokumentet antingen med Microsoft Word eller Aspose.Words.
loadOptions.MswVersion = MsWordVersion.Word2007;
Document doc = new Document(MyDir + "Document.docx", loadOptions);

// Stilens radavstånd kommer att ha detta värde när den laddas av Microsoft Word 2007-specifikationen.
Assert.AreEqual(12.95d, doc.Styles.DefaultParagraphFormat.LineSpacing, 0.01d);
```

### Se även

* enum [MsWordVersion](../../../aspose.words.settings/mswordversion/)
* class [LoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../loadoptions/)
* hopsättning [Aspose.Words](../../../)


