---
title: SaveOptions.AllowEmbeddingPostScriptFonts
second_title: Aspose.Words for .NET API Referansı
description: SaveOptions mülk. TrueType yazı tiplerini bir belgeye gömerken PostScript anahatlarıyla yazı tiplerinin gömülmesine izin verilip verilmeyeceğini belirten bir boole değeri alır veya ayarlar. Varsayılan değer şudur yanlış .
type: docs
weight: 20
url: /tr/net/aspose.words.saving/saveoptions/allowembeddingpostscriptfonts/
---
## SaveOptions.AllowEmbeddingPostScriptFonts property

TrueType yazı tiplerini bir belgeye gömerken PostScript anahatlarıyla yazı tiplerinin gömülmesine izin verilip verilmeyeceğini belirten bir boole değeri alır veya ayarlar. Varsayılan değer şudur: **yanlış** .

```csharp
public bool AllowEmbeddingPostScriptFonts { get; set; }
```

### Notlar

Word, PostScript yazı tiplerini gömmez, ancak bu türde gömülü yazı tiplerine sahip belgeleri açabilir.

Bu seçenek yalnızca şu durumlarda çalışır:[`EmbedTrueTypeFonts`](../../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) the [`FontInfos`](../../../aspose.words/documentbase/fontinfos/) özellik olarak ayarlandı`doğru`.

### Örnekler

Belgenin PostScript yazı tipiyle nasıl kaydedileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "PostScriptFont";
builder.Writeln("Some text with PostScript font.");

// Belgede kullanmak için yazı tipini PostScript ile yükleyin.
MemoryFontSource otf = new MemoryFontSource(File.ReadAllBytes(FontsDir + "AllegroOpen.otf"));
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] { otf });

// TrueType yazı tiplerini göm.
doc.FontInfos.EmbedTrueTypeFonts = true;

// TrueType yazı tiplerini gömerken PostScript yazı tiplerini gömmeye izin ver.
// Microsoft Word, PostScript yazı tiplerini gömmez, ancak bu tür gömülü yazı tiplerine sahip belgeleri açabilir.
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Docx);
saveOptions.AllowEmbeddingPostScriptFonts = true;

doc.Save(ArtifactsDir + "Document.AllowEmbeddingPostScriptFonts.docx", saveOptions);
```

### Ayrıca bakınız

* class [SaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../saveoptions/)
* toplantı [Aspose.Words](../../../)


