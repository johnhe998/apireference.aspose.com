---
title: PrinterSettingsContainer.PrinterSettingsContainer
second_title: Aspose.Words for .NET API Referansı
description: PrinterSettingsContainer inşaatçı. Şunun için bir kapsayıcı oluştururPrinterSettings .
type: docs
weight: 10
url: /tr/net/aspose.words.rendering/printersettingscontainer/printersettingscontainer/
---
## PrinterSettingsContainer constructor

Şunun için bir kapsayıcı oluşturur:PrinterSettings .

```csharp
public PrinterSettingsContainer(PrinterSettings settings)
```

### Örnekler

Yazıcınızın kağıt kaynaklarına ve boyutlarına nasıl erişileceğini ve bunların listeleneceğini gösterir.

```csharp
// "PrinterSettingsContainer", bir "PrinterSettings" nesnesi içeriyor,
// farklı yazıcı sürücüleri için benzersiz veriler içeren.
PrinterSettingsContainer container = new PrinterSettingsContainer(new PrinterSettings());

Console.WriteLine($"This printer contains {container.PaperSources.Count} printer paper sources:");
foreach (PaperSource paperSource in container.PaperSources)
{
    bool isDefault = container.DefaultPageSettingsPaperSource.SourceName == paperSource.SourceName;
    Console.WriteLine($"\t{paperSource.SourceName}, " +
                      $"RawKind: {paperSource.RawKind} {(isDefault ? "(Default)" : "")}");
}

// "PaperSizes" özelliği, yazıcıya kullanması talimatını verecek kağıt boyutlarının listesini içerir.
// Hem PrinterSource hem de PrinterSize bir "RawKind" özelliği içerir,
// bu, PaperSourceKind enum'da listelenen bir kağıt türüne eşittir.
// Yazdırılan sayfa ile aynı "RawKind" değerine sahip bir kağıt kaynağı varsa,
// yazıcı, sağlanan kağıt kaynağını ve boyutunu kullanarak sayfayı yazdıracaktır.
// Aksi takdirde, yazıcı varsayılan olarak "DefaultPageSettingsPaperSource" özelliği tarafından belirlenen kaynağa geçer.
Console.WriteLine($"{container.PaperSizes.Count} paper sizes:");
foreach (System.Drawing.Printing.PaperSize paperSize in container.PaperSizes)
{
    Console.WriteLine($"\t{paperSize}, RawKind: {paperSize.RawKind}");
}
```

### Ayrıca bakınız

* class [PrinterSettingsContainer](../)
* ad alanı [Aspose.Words.Rendering](../../printersettingscontainer/)
* toplantı [Aspose.Words](../../../)


