---
title: Font.ClearFormatting
second_title: Aspose.Words for .NET API Referansı
description: Font yöntem. Varsayılan yazı tipi biçimlendirmesine sıfırlanır.
type: docs
weight: 550
url: /tr/net/aspose.words/font/clearformatting/
---
## Font.ClearFormatting method

Varsayılan yazı tipi biçimlendirmesine sıfırlanır.

```csharp
public void ClearFormatting()
```

### Notlar

that nesnesinde açıkça belirtilen tüm yazı tipi biçimlendirmesini kaldırır **Yazı tipi** yazı tipi biçimlendirmesi uygun üst öğeden devralınacak şekilde elde edildi.

### Örnekler

Köprü alanının nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("For more information, please visit the ");

// Bir köprü ekleyin ve özel biçimlendirme ile vurgulayın.
// Köprü, bizi URL'de belirtilen konuma götürecek tıklanabilir bir metin parçası olacaktır.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Google website", "https://www.google.com", yanlış);
builder.Font.ClearFormatting();
builder.Writeln(".");

// Microsoft Word'deki metindeki bağlantıya Ctrl + sol tıklamak bizi yeni bir web tarayıcı penceresi aracılığıyla URL'ye götürecektir.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlink.docx");
```

### Ayrıca bakınız

* class [Font](../)
* ad alanı [Aspose.Words](../../font/)
* toplantı [Aspose.Words](../../../)


