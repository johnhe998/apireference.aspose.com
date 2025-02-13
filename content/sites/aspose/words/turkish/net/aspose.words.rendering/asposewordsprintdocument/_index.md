---
title: Class AsposeWordsPrintDocument
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Rendering.AsposeWordsPrintDocument sınıf. Bir belgenin yazdırılması için varsayılan bir uygulama sağlar.Document .NET yazdırma çerçevesi içinde .
type: docs
weight: 4280
url: /tr/net/aspose.words.rendering/asposewordsprintdocument/
---
## AsposeWordsPrintDocument class

Bir belgenin yazdırılması için varsayılan bir uygulama sağlar.[`Document`](../../aspose.words/document/) .NET yazdırma çerçevesi içinde .

```csharp
public class AsposeWordsPrintDocument : PrintDocument
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [AsposeWordsPrintDocument](asposewordsprintdocument/)(Document) | Bu sınıfın yeni bir örneğini başlatır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [CachePrinterSettings](../../aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/)() | Şunun bazı alanlarını okur ve önbelleğe alır:PrinterSettings yazdırma süresini azaltmak için. |

### Notlar

`AsposeWordsPrintDocument` geçersiz kılarPrintEventArgs) içinde belirtilen sayfa aralığını yazdırmak içinPrinterSettings.

Tek bir Word belgesi, farklı boyutlara, yönüne ve kağıt tepsilerine sahip sayfaları belirten birden çok bölümden oluşabilir.`AsposeWordsPrintDocument` geçersiz kılar QueryPageSettingsEventArgs) Word belgesi yazdırırken kağıt boyutunu, oryantasyon ve kağıt kaynağını doğru şekilde seçmek için.

Microsoft Word, kağıt tepsileri için yazıcıya özgü değerleri bir Word belgesinde saklar ve bu nedenle, yalnızca kullanıcı kağıt tepsilerini belirttiğinde seçilen yazıcı modeliyle aynı yazıcı modelinde yazdırma, doğru tepsilerden yazdırmayla sonuçlanır. Bir belgeyi farklı bir yazıcıda yazdırırsanız, büyük olasılıkla belgede belirtilen tepsiler değil varsayılan kağıt tepsisi kullanılacaktır.

### Ayrıca bakınız

* ad alanı [Aspose.Words.Rendering](../../aspose.words.rendering/)
* toplantı [Aspose.Words](../../)


