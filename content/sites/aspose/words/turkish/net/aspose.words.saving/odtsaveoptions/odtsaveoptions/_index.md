---
title: OdtSaveOptions.OdtSaveOptions
second_title: Aspose.Words for .NET API Referansı
description: OdtSaveOptions inşaatçı. Dosyaya bir belgeyi kaydetmek için kullanılabilecek bu sınıfın yeni bir örneğini başlatır.Odt biçim.
type: docs
weight: 10
url: /tr/net/aspose.words.saving/odtsaveoptions/odtsaveoptions/
---
## OdtSaveOptions() {#constructor}

Dosyaya bir belgeyi kaydetmek için kullanılabilecek bu sınıfın yeni bir örneğini başlatır.Odt biçim.

```csharp
public OdtSaveOptions()
```

### Örnekler

Kaydedilmiş bir belgenin nasıl daha eski bir ODT şemasına uygun hale getirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = OdtSaveMeasureUnit.Centimeters,
    IsStrictSchema11 = exportToOdt11Specs
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### Ayrıca bakınız

* class [OdtSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../odtsaveoptions/)
* toplantı [Aspose.Words](../../../)

---

## OdtSaveOptions(string) {#constructor_2}

Dosyaya bir belgeyi kaydetmek için kullanılabilecek bu sınıfın yeni bir örneğini başlatır.Odt format bir parola ile şifrelenir.

```csharp
public OdtSaveOptions(string password)
```

### Ayrıca bakınız

* class [OdtSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../odtsaveoptions/)
* toplantı [Aspose.Words](../../../)

---

## OdtSaveOptions(SaveFormat) {#constructor_1}

Dosyaya bir belgeyi kaydetmek için kullanılabilecek bu sınıfın yeni bir örneğini başlatır.Odt or Ott biçim.

```csharp
public OdtSaveOptions(SaveFormat saveFormat)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| saveFormat | SaveFormat | OlabilirOdt veyaOtt. |

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

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [OdtSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../odtsaveoptions/)
* toplantı [Aspose.Words](../../../)


