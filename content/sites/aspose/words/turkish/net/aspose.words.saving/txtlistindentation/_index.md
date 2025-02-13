---
title: Class TxtListIndentation
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.TxtListIndentation sınıf. Belge dışa aktarılırken liste düzeylerinin nasıl girintilendiğini belirtir.Text biçim.
type: docs
weight: 5370
url: /tr/net/aspose.words.saving/txtlistindentation/
---
## TxtListIndentation class

Belge dışa aktarılırken liste düzeylerinin nasıl girintilendiğini belirtir.Text biçim.

```csharp
public class TxtListIndentation
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [TxtListIndentation](txtlistindentation/)() | Default_Constructor |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Character](../../aspose.words.saving/txtlistindentation/character/) { get; set; } | Liste düzeylerini girintilemek için hangi karakterin kullanılacağını alır veya ayarlar. Varsayılan değer '\0'dır, bu, girinti olmadığı anlamına gelir. |
| [Count](../../aspose.words.saving/txtlistindentation/count/) { get; set; } | Kaç tane alır veya ayarlar[`Character`](./character/) bir liste düzeyi için girinti olarak kullanmak için. Varsayılan değer 0'dır, bu, girinti olmadığı anlamına gelir. |

### Örnekler

Bir belgeyi düz metne kaydederken liste girintisinin nasıl yapılandırılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Üç seviyeli girintili bir liste oluşturun.
builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.ListFormat.ListIndent();
builder.Writeln("Item 2");
builder.ListFormat.ListIndent(); 
builder.Write("Item 3");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "TxtSaveOptions" nesnesi oluşturun
// belgeyi düz metne kaydetme şeklimizi değiştirmek için.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// Kullanılacak bir karakter atamak için "Karakter" özelliğini ayarlayın
// liste girintisini düz metinde simüle eden dolgu için.
txtSaveOptions.ListIndentation.Character = ' ';

// Sayıyı belirtmek için "Count" özelliğini ayarlayın
// her liste girinti düzeyi için dolgu karakteri yerleştirmek için.
txtSaveOptions.ListIndentation.Count = 3;

doc.Save(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt");

Assert.AreEqual("1. Item 1\r\n" +
                "   a. Item 2\r\n" +
                "      i. Item 3\r\n", docText);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


