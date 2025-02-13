---
title: OdtSaveOptions.Password
second_title: Aspose.Words for .NET API Referansı
description: OdtSaveOptions mülk. Belgeyi şifrelemek için bir parola alır veya ayarlar.
type: docs
weight: 40
url: /tr/net/aspose.words.saving/odtsaveoptions/password/
---
## OdtSaveOptions.Password property

Belgeyi şifrelemek için bir parola alır veya ayarlar.

```csharp
public string Password { get; set; }
```

### Notlar

Belgeyi şifreleme olmadan kaydetmek için bu özellik boş veya boş dize olmalıdır.

### Örnekler

Kaydedilmiş bir ODT/OTT belgesinin bir parola ile nasıl şifreleneceğini ve ardından Aspose.Words kullanarak nasıl yükleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Yeni bir OdtSaveOptions oluşturun ve "SaveFormat.Odt" iletin,
// veya belgenin kaydedileceği format olarak "SaveFormat.Ott". 
OdtSaveOptions saveOptions = new OdtSaveOptions(saveFormat);
saveOptions.Password = "@sposeEncrypted_1145";

string extensionString = FileFormatUtil.SaveFormatToExtension(saveFormat);

// Bu dökümanı uygun bir editör ile açarsak,
// SaveOptions nesnesinde belirttiğimiz şifreyi soracaktır.
doc.Save(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString, saveOptions);

FileFormatInfo docInfo = FileFormatUtil.DetectFileFormat(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString);

Assert.IsTrue(docInfo.IsEncrypted);

// Bu belgeyi Aspose.Words kullanarak tekrar açmak veya düzenlemek istersek,
// Yükleme yapıcısına doğru parolayı içeren bir LoadOptions nesnesi sağlamamız gerekecek.
doc = new Document(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString,
    new LoadOptions("@sposeEncrypted_1145"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Ayrıca bakınız

* class [OdtSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../odtsaveoptions/)
* toplantı [Aspose.Words](../../../)


