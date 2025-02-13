---
title: FontSavingArgs.IsSubsettingNeeded
second_title: Aspose.Words for .NET API Referansı
description: FontSavingArgs mülk. Bir yazı tipi kaynağı olarak dışa aktarmadan önce mevcut yazı tipinin alt kümelenip alt küme oluşturulmayacağını belirlemeye izin verir.
type: docs
weight: 70
url: /tr/net/aspose.words.saving/fontsavingargs/issubsettingneeded/
---
## FontSavingArgs.IsSubsettingNeeded property

Bir yazı tipi kaynağı olarak dışa aktarmadan önce mevcut yazı tipinin alt kümelenip alt küme oluşturulmayacağını belirlemeye izin verir.

```csharp
public bool IsSubsettingNeeded { get; set; }
```

### Notlar

Yazı tipleri, eksiksiz orijinal yazı tipi dosyaları olarak dışa aktarılabilir veya yalnızca belgede kullanılan karakter karakterlerini içerecek şekilde alt kümelere ayrılabilir. Alt kümeleme, sonuçta ortaya çıkan yazı tipi kaynak boyutunun küçültülmesine olanak tanır.

Varsayılan olarak, Aspose.Words, orijinal yazı tipi dosya boyutu ile aşağıda belirtilen dosya boyutunu karşılaştırarak alt kümeleme yapılıp yapılmayacağına karar verir.[`FontResourcesSubsettingSizeThreshold`](../../htmlsaveoptions/fontresourcessubsettingsizethreshold/) . Bu davranışı tek tek yazı tipleri için geçersiz kılabilirsiniz.`IsSubsettingNeeded` Emlak.

### Örnekler

HTML'ye kaydederken yazı tiplerini dışa aktarmak için özel mantığın nasıl tanımlanacağını gösterir.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Fontları ayrı dosyalara aktarmak için bir SaveOptions nesnesi yapılandırın.
    // Yazı tipi kaydetmeyi özel bir şekilde gerçekleştirecek bir geri arama ayarlayın.
    HtmlSaveOptions options = new HtmlSaveOptions
    {
        ExportFontResources = true,
        FontSavingCallback = new HandleFontSaving()
    };

    // Geri arama, .ttf dosyalarını dışa aktaracak ve bunları çıktı belgesinin yanına kaydedecektir.
    doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveExportedFonts.html", options);

    foreach (string fontFilename in Array.FindAll(Directory.GetFiles(ArtifactsDir), s => s.EndsWith(".ttf")))
    {
        Console.WriteLine(fontFilename);
    }

/// <summary>
/// Dışa aktarılan yazı tipleriyle ilgili bilgileri yazdırır ve bunları çıktıları .html ile aynı yerel sistem klasörüne kaydeder.
/// </summary>
public class HandleFontSaving : IFontSavingCallback
{
    void IFontSavingCallback.FontSaving(FontSavingArgs args)
    {
        Console.Write($"Font:\t{args.FontFamilyName}");
        if (args.Bold) Console.Write(", bold");
        if (args.Italic) Console.Write(", italic");
        Console.WriteLine($"\nSource:\t{args.OriginalFileName}, {args.OriginalFileSize} bytes\n");

        // Kaynak belgeye buradan da ulaşabiliriz.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        Assert.True(args.IsExportNeeded);
        Assert.True(args.IsSubsettingNeeded);

        // Dışa aktarılan bir yazı tipini kaydetmenin iki yolu vardır.
        // 1 - Yerel bir dosya sistemi konumuna kaydedin:
        args.FontFileName = args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last();

        // 2 - Bir akışa kaydedin:
        args.FontStream =
            new FileStream(ArtifactsDir + args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last(), FileMode.Create);
        Assert.False(args.KeepFontStreamOpen);
    }
}
```

### Ayrıca bakınız

* class [FontSavingArgs](../)
* ad alanı [Aspose.Words.Saving](../../fontsavingargs/)
* toplantı [Aspose.Words](../../../)


