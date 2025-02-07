---
title: Interface IDocumentLoadingCallback
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Loading.IDocumentLoadingCallback arayüz. Bir belgeyi yüklerken kendi özel yönteminizin çağrılmasını istiyorsanız bu arayüzü uygulayın.
type: docs
weight: 3430
url: /tr/net/aspose.words.loading/idocumentloadingcallback/
---
## IDocumentLoadingCallback interface

Bir belgeyi yüklerken kendi özel yönteminizin çağrılmasını istiyorsanız bu arayüzü uygulayın.

```csharp
public interface IDocumentLoadingCallback
```

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Notify](../../aspose.words.loading/idocumentloadingcallback/notify/)(DocumentLoadingArgs) | Bu, belge yükleme ilerlemesini bildirmek için çağrılır. |

### Örnekler

Belge yüklemesi, beklenen yükleme süresini aştığında kullanıcıya nasıl bildirileceğini gösterir.

```csharp
[Test]
public void ProgressCallback()
{
    LoadingProgressCallback progressCallback = new LoadingProgressCallback();

    LoadOptions loadOptions = new LoadOptions { ProgressCallback = progressCallback };

    try
    {
        Document doc = new Document(MyDir + "Big document.docx", loadOptions);
    }
    catch (OperationCanceledException exception)
    {
        Console.WriteLine(exception.Message);

        // Yükleme süresi sorununu ele al.
    }
}

/// <summary>
/// "MaxDuration" saniyesinden sonra bir belge yüklemesini iptal edin.
/// </summary>
public class LoadingProgressCallback : IDocumentLoadingCallback
{
    /// <summary>
    /// Ktr.
    /// </summary>
    public LoadingProgressCallback()
    {
        mLoadingStartedAt = DateTime.Now;
    }

    /// <summary>
    /// Belge yükleme sırasında çağrılan geri arama yöntemi.
    /// </summary>
    /// <param name="args">Argümanlar yükleniyor.</param>
    public void Notify(DocumentLoadingArgs args)
    {
        DateTime canceledAt = DateTime.Now;
        double ellapsedSeconds = (canceledAt - mLoadingStartedAt).TotalSeconds;

        if (ellapsedSeconds > MaxDuration)
            throw new OperationCanceledException($"EstimatedProgress = {args.EstimatedProgress}; CanceledAt = {canceledAt}");
    }

    /// <summary>
    /// Belge yüklemenin başladığı tarih ve saat.
    /// </summary>
    private readonly DateTime mLoadingStartedAt;

    /// <summary>
    /// Saniye cinsinden izin verilen maksimum süre.
    /// </summary>
    private const double MaxDuration = 0.5;
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Loading](../../aspose.words.loading/)
* toplantı [Aspose.Words](../../)


