---
title: Class WriteProtection
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Settings.WriteProtection sınıf. Bir belge için yazma koruması ayarlarını belirtir.
type: docs
weight: 5670
url: /tr/net/aspose.words.settings/writeprotection/
---
## WriteProtection class

Bir belge için yazma koruması ayarlarını belirtir.

```csharp
public class WriteProtection
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [IsWriteProtected](../../aspose.words.settings/writeprotection/iswriteprotected/) { get; } | Yazma koruması parolası ayarlandığında doğru döndürür. |
| [ReadOnlyRecommended](../../aspose.words.settings/writeprotection/readonlyrecommended/) { get; set; } | Belge yazarının belgenin salt okunur olarak açılmasını tavsiye edip etmediğini belirtir. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [SetPassword](../../aspose.words.settings/writeprotection/setpassword/)(string) | Belge için yazma koruması parolasını ayarlar. |
| [ValidatePassword](../../aspose.words.settings/writeprotection/validatepassword/)(string) | Belirtilen parola, belgenin korunduğu yazma koruması parolasıyla aynıysa true döndürür. Belge parolayla yazmaya karşı korumalı değilse false döndürür. |

### Notlar

Yazma koruması, yazarın belgenin salt okunur olarak açılmasını tavsiye edip etmediğini ve/veya bir belgeyi değiştirmek için bir parola gerektirip gerektirmediğini belirtir.

Yazma koruması, belge korumasından farklıdır. Yazma koruması, Microsoft Word'de Farklı Kaydet iletişim kutusunun seçeneklerinde belirtilir.

Bu sınıfın örneklerini doğrudan oluşturmazsınız. Belge koruma ayarlarına şu adresten erişirsiniz:[`WriteProtection`](../../aspose.words/document/writeprotection/) Emlak.

### Örnekler

Bir belgenin parolayla nasıl korunacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! This document is protected.");

// En fazla 15 karakter uzunluğunda bir parola girin ve ardından belgenin koruma durumunu doğrulayın.
doc.WriteProtection.SetPassword("MyPassword");
doc.WriteProtection.ReadOnlyRecommended = true;

Assert.IsTrue(doc.WriteProtection.IsWriteProtected);
Assert.IsTrue(doc.WriteProtection.ValidatePassword("MyPassword"));

// Koruma, belgenin programlı olarak düzenlenmesini engellemez ve içeriği şifrelemez.
doc.Save(ArtifactsDir + "Document.WriteProtection.docx");
doc = new Document(ArtifactsDir + "Document.WriteProtection.docx");

Assert.IsTrue(doc.WriteProtection.IsWriteProtected);

builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.Writeln("Writing text in a protected document.");

Assert.AreEqual("Hello world! This document is protected." +
                "\rWriting text in a protected document.", doc.GetText().Trim());
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Settings](../../aspose.words.settings/)
* toplantı [Aspose.Words](../../)


