---
title: HtmlLoadOptions.WebRequestTimeout
second_title: Aspose.Words for .NET API Referansı
description: HtmlLoadOptions mülk. Web isteğinin zaman aşımına uğramadan önce beklenecek milisaniye sayısı. Varsayılan değer 100.000 milisaniyedir 100 saniye.
type: docs
weight: 70
url: /tr/net/aspose.words.loading/htmlloadoptions/webrequesttimeout/
---
## HtmlLoadOptions.WebRequestTimeout property

Web isteğinin zaman aşımına uğramadan önce beklenecek milisaniye sayısı. Varsayılan değer 100.000 milisaniyedir (100 saniye).

```csharp
public int WebRequestTimeout { get; set; }
```

### Notlar

HTML ve MHTML belgelerinde bağlantılı harici kaynaklar (resimler, style sayfaları) yüklenirken Aspose.Words'ün yanıt beklediği milisaniye sayısı.

### Örnekler

URL'lerle bağlantılı harici kaynaklara sahip bir belge yüklenirken web istekleri için bir zaman sınırının nasıl ayarlanacağını gösterir.

```csharp
{
    // Yeni bir HtmlLoadOptions nesnesi oluşturun ve bir web isteği için zaman aşımı eşiğini doğrulayın.
    HtmlLoadOptions options = new HtmlLoadOptions();

    // Bir web adresi URL'si ile harici olarak bağlantılı kaynaklara sahip bir Html belgesi yüklerken,
    // Aspose.Words bu süre içinde kaynakları getiremeyen web isteklerini milisaniye cinsinden iptal eder.
    Assert.AreEqual(100000, options.WebRequestTimeout);

    // Yükleme sırasında oluşan tüm uyarıları kaydedecek bir WarningCallback ayarlayın.
    ListDocumentWarnings warningCallback = new ListDocumentWarnings();
    options.WarningCallback = warningCallback;

    // Böyle bir belgeyi yükleyin ve görüntü verileriyle bir şeklin oluşturulduğunu doğrulayın.
    // Bu bağlantılı resmin yüklenmesi için bir web isteği gerekecek ve bu istek bizim zaman sınırımız içinde tamamlanacak.
    string html = $@"
        <html>
            <img src=""{ImageUrl}"" alt=""Aspose logo"" style=""width:400px;height:400px;"">
        </html>
    ";

    // Mantıksız bir zaman aşımı sınırı ayarlayın ve belgeyi yeniden yüklemeyi deneyin.
    options.WebRequestTimeout = 0;
    Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), options);
    Assert.AreEqual(2, warningCallback.Warnings().Count);

    // Zaman sınırı içinde bir görüntü elde edemeyen bir web isteği yine de bir görüntü üretecektir.
    // Ancak, resim genellikle eksik resimleri ifade eden kırmızı 'x' olacaktır.
    Shape imageShape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
    Assert.AreEqual(924, imageShape.ImageData.ImageBytes.Length);

    // Zaman aşımına uğramış web isteklerinden gelen uyarıları almak için özel bir geri arama da yapılandırabiliriz.
    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[0].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[0].WarningType);
    Assert.AreEqual($"Couldn't load a resource from \'{ImageUrl}\'.", warningCallback.Warnings()[0].Description);

    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[1].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[1].WarningType);
    Assert.AreEqual("Image has been replaced with a placeholder.", warningCallback.Warnings()[1].Description);

    doc.Save(ArtifactsDir + "HtmlLoadOptions.WebRequestTimeout.docx");
}

/// <summary>
/// Belge yükleme işlemi sırasında oluşan tüm uyarıları bir Listede saklar.
/// </summary>
private class ListDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        mWarnings.Add(info);
    }

    public List<WarningInfo> Warnings() { 
        return mWarnings;
    }

    private readonly List<WarningInfo> mWarnings = new List<WarningInfo>();
}
```

### Ayrıca bakınız

* class [HtmlLoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../htmlloadoptions/)
* toplantı [Aspose.Words](../../../)


