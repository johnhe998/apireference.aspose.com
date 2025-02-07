---
title: ChmLoadOptions.OriginalFileName
second_title: Aspose.Words for .NET API Referansı
description: ChmLoadOptions mülk. CHM dosyasının adı. Varsayılan değerhükümsüz .
type: docs
weight: 20
url: /tr/net/aspose.words.loading/chmloadoptions/originalfilename/
---
## ChmLoadOptions.OriginalFileName property

CHM dosyasının adı. Varsayılan değer`hükümsüz` .

```csharp
public string OriginalFileName { get; set; }
```

### Notlar

CHM belgeleri, dosya adına göre aynı belgeye başvuran bağlantılar içerebilir. Aspose.Words bu tür bağlantıları destekler ve normalde[`OriginalFileName`](../../../aspose.words/document/originalfilename/) link tarafından başvurulan dosyanın yüklenmekte olan dosya olup olmadığını kontrol etmek için. Bir belge bir akıştan yüklenirse, otomatik olarak belirlenemeyeceğinden orijinal dosya adı bu özellik aracılığıyla açıkça belirtilmelidir .

Bir dosyadan bir CHM belgesi yüklenirse ve bu özellik için boş olmayan bir değer belirtilirse, değer, içinde depolanan dosyanın gerçek adına göre önceliğini alır.[`OriginalFileName`](../../../aspose.words/document/originalfilename/) .

### Örnekler

"ms-its:myfile.chm::/index.htm" gibi URL'lerin nasıl çözüleceğini gösterir.

```csharp
// Belgemiz "ms-its:amhelp.chm::....htm" gibi URL'ler içeriyor, ancak adı farklı,
// böylece dosya bağlantıları HTML'ye kaydettikten sonra çalışmaz.
// Bu davranışı önlemek için orijinal dosya adını 'ChmLoadOptions' içinde tanımlamamız gerekiyor.
ChmLoadOptions loadOptions = new ChmLoadOptions { OriginalFileName = "amhelp.chm" };

Document doc = new Document(new MemoryStream(File.ReadAllBytes(MyDir + "Document with ms-its links.chm")),
    loadOptions);

doc.Save(ArtifactsDir + "ExChmLoadOptions.OriginalFileName.html");
```

### Ayrıca bakınız

* class [ChmLoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../chmloadoptions/)
* toplantı [Aspose.Words](../../../)


