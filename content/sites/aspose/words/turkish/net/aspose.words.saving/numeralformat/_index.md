---
title: Enum NumeralFormat
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.NumeralFormat Sıralama. Sabit sayfa biçimlerinde oluşturulurken sayıları temsil etmek için kullanılan simge kümesini belirtir.
type: docs
weight: 5030
url: /tr/net/aspose.words.saving/numeralformat/
---
## NumeralFormat enumeration

Sabit sayfa biçimlerinde oluşturulurken sayıları temsil etmek için kullanılan simge kümesini belirtir.

```csharp
public enum NumeralFormat
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| European | `0` | Avrupa rakamları: 0123456789. |
| ArabicIndic | `1` | Arapça kullanılan rakamlar: ٠١٢٣٤٥٦٧٨٩. Unicode aralığı U+0660 - u+0669. |
| EasternArabicIndic | `2` | Farsça ve Urduca kullanılan sayılar: ۰۱۲۳۴۵۶۷۸۹. Unicode aralığı U+06F0 - u+06F9. |
| Context | `3` | Sembol kümesine bağlamdan (yerel ayar ve RTL özelliği) karar verilir. |
| System | `4` | BU SEÇENEK DESTEKLENMEMEKTEDİR. Sembol kümesine bölgesel ayarlardan karar verilir. |

### Örnekler

PDF'ye kaydederken kullanılan sayı biçiminin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = new CultureInfo("ar-AR").LCID;
builder.Writeln("1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 50, 100");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// "NumeralFormat" özelliğini "NumeralFormat.ArabicIndic" olarak ayarlayın.
// U+0660 ila U+0669 aralığındaki glifleri sayı olarak kullanın.
// "NumeralFormat" özelliğini "NumeralFormat.Context" olarak ayarlayın.
// kaç glif kullanılacağını belirlemek için yerel ayara bakın.
// "NumeralFormat" özelliğini "NumeralFormat.EasternArabicIndic" olarak ayarlayın.
// U+06F0 ila U+06F9 aralığındaki glifleri sayı olarak kullanın.
// Avrupa rakamlarını kullanmak için "NumeralFormat" özelliğini "NumeralFormat.European" olarak ayarlayın.
// Sembol setini bölgesel ayarlardan belirlemek için "NumeralFormat" özelliğini "NumeralFormat.System" olarak ayarlayın.
options.NumeralFormat = numeralFormat;

doc.Save(ArtifactsDir + "PdfSaveOptions.SetNumeralFormat.pdf", options);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


