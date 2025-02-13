---
title: Enum ReportBuildOptions
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Reporting.ReportBuildOptions Sıralama. davranışını kontrol eden seçenekleri belirtir.ReportingEngine bir rapor oluştururken.
type: docs
weight: 4460
url: /tr/net/aspose.words.reporting/reportbuildoptions/
---
## ReportBuildOptions enumeration

davranışını kontrol eden seçenekleri belirtir.[`ReportingEngine`](../reportingengine/) bir rapor oluştururken.

```csharp
[Flags]
public enum ReportBuildOptions
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Varsayılan seçenekleri belirtir. |
| AllowMissingMembers | `1` | Eksik nesne üyelerinin motor tarafından boş sabit değerler olarak ele alınması gerektiğini belirtir. Bu seçenek yalnızca örnek (yani, statik olmayan) nesne üyelerine ve uzantı yöntemlerine erişimi etkiler. Bu seçeneği ayarlanmazsa, eksik bir nesne üyesiyle karşılaştığında motor bir istisna atar. |
| RemoveEmptyParagraphs | `2` | Şablon sözdizimi etiketleri kaldırıldıktan veya boş değerlerle değiştirildikten sonra, motorun boş kalan paragrafları kaldırması gerektiğini belirtir. |
| InlineErrorMessages | `4` | Motorun şablon sözdizimi hata mesajlarını çıktı belgelerine satır içi olarak eklemesi gerektiğini belirtir. Bu seçenek ayarlanmazsa, motor bir sözdizimi hatasıyla karşılaştığında bir istisna atar. |
| UseLegacyHeaderFooterVisiting | `8` | Motorun, Aspose.Words 21.9. 'den önceki sürümleriyle uyumlu order bölümündeki alt düğümleri (üstbilgiler, altbilgiler, gövdeler) ziyaret etmesi gerektiğini belirtir. |
| RespectJpegExifOrientation | `10` | Eklenen JPEG görüntülerini uygun şekilde döndürmek için motorun EXIF ​​​​görüntü yönlendirme değerlerini kullanması gerektiğini belirtir. |

### Ayrıca bakınız

* ad alanı [Aspose.Words.Reporting](../../aspose.words.reporting/)
* toplantı [Aspose.Words](../../)


