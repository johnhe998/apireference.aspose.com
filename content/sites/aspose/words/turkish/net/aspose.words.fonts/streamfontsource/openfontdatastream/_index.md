---
title: StreamFontSource.OpenFontDataStream
second_title: Aspose.Words for .NET API Referansı
description: StreamFontSource yöntem. Bu yöntem isteğe bağlı olarak yazı tipi verileriyle akışı açmalıdır.
type: docs
weight: 30
url: /tr/net/aspose.words.fonts/streamfontsource/openfontdatastream/
---
## StreamFontSource.OpenFontDataStream method

Bu yöntem, isteğe bağlı olarak yazı tipi verileriyle akışı açmalıdır.

```csharp
public abstract Stream OpenFontDataStream()
```

### Geri dönüş değeri

Yazı tipi veri akışı.

### Notlar

Akış, okunduktan sonra kapatılacak. Açıkça kapatmaya gerek yok.

### Örnekler

Akıştan yazı tiplerinin nasıl yükleneceğini gösterir.

```csharp
{
    FontSettings fontSettings = new FontSettings();
    fontSettings.SetFontsSources(new FontSourceBase[] {new StreamFontSourceFile()});

    DocumentBuilder builder = new DocumentBuilder();
    builder.Document.FontSettings = fontSettings;
    builder.Font.Name = "Kreon-Regular";
    builder.Writeln("Test aspose text when saving to PDF.");

    builder.Document.Save(ArtifactsDir + "FontSettings.StreamFontSourceFileRendering.pdf");
}

/// <summary>
/// Yazı tipi verilerini bellekte saklamak yerine yalnızca gerektiğinde yükleyin
/// "FontSettings" nesnesinin tüm kullanım ömrü boyunca.
/// </summary>
private class StreamFontSourceFile : StreamFontSource
{
    public override Stream OpenFontDataStream()
    {
        return File.OpenRead(FontsDir + "Kreon-Regular.ttf");
    }
}
```

### Ayrıca bakınız

* class [StreamFontSource](../)
* ad alanı [Aspose.Words.Fonts](../../streamfontsource/)
* toplantı [Aspose.Words](../../../)


