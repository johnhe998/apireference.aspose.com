---
title: PageInfo.GetDotNetPaperSize
second_title: Aspose.Words for .NET API Referansı
description: PageInfo yöntem. PaperSize bununla temsil edilen sayfayı yazdırmak için uygun nesne PageInfo .
type: docs
weight: 70
url: /tr/net/aspose.words.rendering/pageinfo/getdotnetpapersize/
---
## PageInfo.GetDotNetPaperSize method

PaperSize bununla temsil edilen sayfayı yazdırmak için uygun nesne [`PageInfo`](../) .

```csharp
public PaperSize GetDotNetPaperSize(PaperSizeCollection paperSizes)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| paperSizes | PaperSizeCollection | Kullanılabilir kağıt boyutları. |

### Geri dönüş değeri

Kağıt boyutunu belirtmek için .NET yazdırma çerçevesinde kullanabileceğiniz bir nesne.

### Örnekler

Aspose.Words belgelerinin yazdırılmasının nasıl özelleştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

    MyPrintDocument printDoc = new MyPrintDocument(doc);
    printDoc.PrinterSettings.PrintRange = System.Drawing.Printing.PrintRange.SomePages;
    printDoc.PrinterSettings.FromPage = 1;
    printDoc.PrinterSettings.ToPage = 1;

    printDoc.Print();
}

/// <summary>
/// Yazdırırken uygun bir kağıt boyutu, yönlendirme ve kağıt tepsisi seçer.
/// </summary>
public class MyPrintDocument : PrintDocument
{
    public MyPrintDocument(Document document)
    {
        mDocument = document;
    }

    /// <summary>
    /// Kullanıcı seçimine göre yazdırılacak sayfa aralığını başlatır.
    /// </summary>
    protected override void OnBeginPrint(PrintEventArgs e)
    {
        base.OnBeginPrint(e);

        switch (PrinterSettings.PrintRange)
        {
            case System.Drawing.Printing.PrintRange.AllPages:
                mCurrentPage = 1;
                mPageTo = mDocument.PageCount;
                break;
            case System.Drawing.Printing.PrintRange.SomePages:
                mCurrentPage = PrinterSettings.FromPage;
                mPageTo = PrinterSettings.ToPage;
                break;
            default:
                throw new InvalidOperationException("Unsupported print range.");
        }
    }

    /// <summary>
    /// Her sayfa yazdırılmadan önce çağrılır. 
    /// </summary>
    protected override void OnQueryPageSettings(QueryPageSettingsEventArgs e)
    {
        base.OnQueryPageSettings(e);

        // Tek bir Microsoft Word belgesi, farklı boyutlarda sayfaları belirten birden çok bölüme sahip olabilir, 
        // yönler ve kağıt tepsileri. .NET yazdırma çerçevesi bu kodu daha önce çağırır. 
        // her sayfa yazdırılır, bu da bize mevcut sayfanın nasıl yazdırılacağını belirleme şansı verir.
        PageInfo pageInfo = mDocument.GetPageInfo(mCurrentPage - 1);
        e.PageSettings.PaperSize = pageInfo.GetDotNetPaperSize(PrinterSettings.PaperSizes);

        // Microsoft Word, her bölüm için kağıt kaynağını (yazıcı tepsisi) yazıcıya özel bir değer olarak saklar.
        // Doğru tepsi değerini elde etmek için, yazıcınızın döndürmesi gereken "RawKind" özelliğini kullanmanız gerekecektir.
        e.PageSettings.PaperSource.RawKind = pageInfo.PaperTray;
        e.PageSettings.Landscape = pageInfo.Landscape;
    }

    /// <summary>
    /// Her sayfanın yazdırılmak üzere işlenmesi için çağrılır. 
    /// </summary>
    protected override void OnPrintPage(PrintPageEventArgs e)
    {
        base.OnPrintPage(e);

        // Aspose.Words render motoru, kağıdın orijininden (x = 0, y = 0) çizilen bir sayfa oluşturur.
        // Yazıcıda her sayfayı oluşturacak sert bir kenar boşluğu olacaktır. Bu sert marjla dengelememiz gerekiyor.
        float hardOffsetX, hardOffsetY;

        // Aşağıda, sabit bir marj ayarlamanın iki yolu bulunmaktadır.
        if (e.PageSettings != null && e.PageSettings.HardMarginX != 0 && e.PageSettings.HardMarginY != 0)
        {
            // 1 - "PageSettings" özelliği ile.
            hardOffsetX = e.PageSettings.HardMarginX;
            hardOffsetY = e.PageSettings.HardMarginY;
        }
        else
        {
            // 2 - "PageSettings" özelliği kullanılamıyorsa kendi değerlerimizi kullanarak.
            hardOffsetX = 20;
            hardOffsetY = 20;
        }

        mDocument.RenderToScale(mCurrentPage, e.Graphics, -hardOffsetX, -hardOffsetY, 1.0f);

        mCurrentPage++;
        e.HasMorePages = mCurrentPage <= mPageTo;
    }

    private readonly Document mDocument;
    private int mCurrentPage;
    private int mPageTo;
}
```

### Ayrıca bakınız

* class [PageInfo](../)
* ad alanı [Aspose.Words.Rendering](../../pageinfo/)
* toplantı [Aspose.Words](../../../)


