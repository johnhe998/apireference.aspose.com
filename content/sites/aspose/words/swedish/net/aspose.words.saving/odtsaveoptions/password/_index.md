---
title: OdtSaveOptions.Password
second_title: Aspose.Words för .NET API Referens
description: OdtSaveOptions fast egendom. Hämtar eller ställer in ett lösenord för att kryptera dokument.
type: docs
weight: 40
url: /sv/net/aspose.words.saving/odtsaveoptions/password/
---
## OdtSaveOptions.Password property

Hämtar eller ställer in ett lösenord för att kryptera dokument.

```csharp
public string Password { get; set; }
```

### Anmärkningar

För att spara dokument utan kryptering bör denna egenskap vara null eller tom sträng.

### Exempel

Visar hur man krypterar ett sparat ODT/OTT-dokument med ett lösenord och sedan laddar det med Aspose.Words.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Skapa ett nytt OdtSaveOptions och skicka antingen "SaveFormat.Odt",
// eller "SaveFormat.Ott" som formatet att spara dokumentet i. 
OdtSaveOptions saveOptions = new OdtSaveOptions(saveFormat);
saveOptions.Password = "@sposeEncrypted_1145";

string extensionString = FileFormatUtil.SaveFormatToExtension(saveFormat);

// Om vi öppnar det här dokumentet med en lämplig redigerare,
// det kommer att fråga oss om lösenordet vi angav i SaveOptions-objektet.
doc.Save(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString, saveOptions);

FileFormatInfo docInfo = FileFormatUtil.DetectFileFormat(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString);

Assert.IsTrue(docInfo.IsEncrypted);

// Om vi vill öppna eller redigera detta dokument igen med Aspose.Words,
// vi måste tillhandahålla ett LoadOptions-objekt med rätt lösenord till laddningskonstruktorn.
doc = new Document(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString,
    new LoadOptions("@sposeEncrypted_1145"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Se även

* class [OdtSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../odtsaveoptions/)
* hopsättning [Aspose.Words](../../../)


