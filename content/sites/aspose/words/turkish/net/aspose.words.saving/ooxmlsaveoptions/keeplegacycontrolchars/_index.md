---
title: OoxmlSaveOptions.KeepLegacyControlChars
second_title: Aspose.Words for .NET API Referansı
description: OoxmlSaveOptions mülk. Eski kontrol karakterlerinin orijinal temsilini tutar.
type: docs
weight: 40
url: /tr/net/aspose.words.saving/ooxmlsaveoptions/keeplegacycontrolchars/
---
## OoxmlSaveOptions.KeepLegacyControlChars property

Eski kontrol karakterlerinin orijinal temsilini tutar.

```csharp
public bool KeepLegacyControlChars { get; set; }
```

### Örnekler

.docx'e dönüştürürken eski kontrol karakterlerinin nasıl destekleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Legacy control character.doc");

// Belgeyi OOXML formatında kaydettiğimizde bir OoxmlSaveOptions nesnesi oluşturabiliriz.
// ve ardından belgeyi kaydetme şeklimizi değiştirmek için belgenin kaydetme yöntemine iletin.
// Korumak için "KeepLegacyControlChars" özelliğini "true" olarak ayarlayın
// kaydederken "ShortDateTime" eski karakteri.
// Kaldırmak için "KeepLegacyControlChars" özelliğini "false" olarak ayarlayın
// çıktı belgesindeki "ShortDateTime" eski karakteri.
OoxmlSaveOptions so = new OoxmlSaveOptions(SaveFormat.Docx);
so.KeepLegacyControlChars = keepLegacyControlChars;

doc.Save(ArtifactsDir + "OoxmlSaveOptions.KeepLegacyControlChars.docx", so);

doc = new Document(ArtifactsDir + "OoxmlSaveOptions.KeepLegacyControlChars.docx");

Assert.AreEqual(keepLegacyControlChars ? "\u0013date \\@ \"MM/dd/yyyy\"\u0014\u0015\f" : "\u001e\f",
    doc.FirstSection.Body.GetText());
```

### Ayrıca bakınız

* class [OoxmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../ooxmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


