---
title: Interface IPageLayoutCallback
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Layout.IPageLayoutCallback arayüz. Sayfa düzeni modelinin oluşturulması ve oluşturulması sırasında kendi özel yönteminizin çağrılmasını istiyorsanız bu arabirimi uygulayın.
type: docs
weight: 3110
url: /tr/net/aspose.words.layout/ipagelayoutcallback/
---
## IPageLayoutCallback interface

Sayfa düzeni modelinin oluşturulması ve oluşturulması sırasında kendi özel yönteminizin çağrılmasını istiyorsanız bu arabirimi uygulayın.

```csharp
public interface IPageLayoutCallback
```

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Notify](../../aspose.words.layout/ipagelayoutcallback/notify/)(PageLayoutCallbackArgs) | Bu, düzen oluşturma ve işleme ilerleme durumunu bildirmek için çağrılır. |

### Notlar

Bu arabirimin birincil kullanımı, uygulama kodunun oluşturma işlemini iptal etmesine izin vermektir.

Belgenin başlangıcında yalnızca birkaç sayfa için sayfa düzeni modeli oluşturmak, ardından işlemi iptal etmek ve yalnızca önceden oluşturulmuş olanı oluşturmak mümkündür.

Ancak, işlem tamamlanmış olsaydı, oluşturma sonuçlarının her sayfa için oluşturulacak sonuçlarla eşleşmeyebileceğini unutmayın.

Bu teknik her belge için çalışmayabilir veya tamamen başarısız olabilir.

### Örnekler

Bir düzen geri çağırma ile düzen değişikliklerinin nasıl izleneceğini gösterir.

```csharp
[Test]
public void PageLayoutCallback()
{
    Document doc = new Document();
    doc.BuiltInDocumentProperties.Title = "My Document";

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.Writeln("Hello world!");

    doc.LayoutOptions.Callback = new RenderPageLayoutCallback();
    doc.UpdatePageLayout();

    doc.Save(ArtifactsDir + "Layout.PageLayoutCallback.pdf");
}

/// <summary>
/// Belgeyi sabit bir sayfa biçiminde kaydettiğimizde bize haber verir
/// ve yerel dosya sistemindeki bir görüntüye sayfa yeniden akışı gerçekleştirdiğimiz bir sayfayı oluşturur.
/// </summary>
private class RenderPageLayoutCallback : IPageLayoutCallback
{
    public void Notify(PageLayoutCallbackArgs a)
    {
        switch (a.Event)
        {
            case PageLayoutEvent.PartReflowFinished:
                NotifyPartFinished(a);
                break;
            case PageLayoutEvent.ConversionFinished:
                NotifyConversionFinished(a);
                break;
        }
    }

    private void NotifyPartFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Part at page {a.PageIndex + 1} reflow.");
        RenderPage(a, a.PageIndex);
    }

    private void NotifyConversionFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Document \"{a.Document.BuiltInDocumentProperties.Title}\" converted to page format.");
    }

    private void RenderPage(PageLayoutCallbackArgs a, int pageIndex)
    {
        ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png) { PageSet = new PageSet(pageIndex) };

        using (FileStream stream =
            new FileStream(ArtifactsDir + $@"PageLayoutCallback.page-{pageIndex + 1} {++mNum}.png",
                FileMode.Create))
            a.Document.Save(stream, saveOptions);
    }

    private int mNum;
}
```

### Ayrıca bakınız

* property [Callback](../layoutoptions/callback/)
* ad alanı [Aspose.Words.Layout](../../aspose.words.layout/)
* toplantı [Aspose.Words](../../)


