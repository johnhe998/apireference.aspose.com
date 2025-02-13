---
title: Class Range
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Range sınıf. Belgedeki bitişik bir alanı temsil eder.
type: docs
weight: 4270
url: /tr/net/aspose.words/range/
---
## Range class

Belgedeki bitişik bir alanı temsil eder.

```csharp
public class Range
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Bookmarks](../../aspose.words/range/bookmarks/) { get; } | Bir döndürür[`Bookmarks`](./bookmarks/) aralığındaki tüm yer işaretlerini temsil eden koleksiyon. |
| [Fields](../../aspose.words/range/fields/) { get; } | Bir döndürür[`Fields`](./fields/) aralıktaki tüm alanları temsil eden koleksiyon. |
| [FormFields](../../aspose.words/range/formfields/) { get; } | Bir döndürür[`FormFields`](./formfields/) aralıktaki tüm form alanlarını temsil eden koleksiyon. |
| [StructuredDocumentTags](../../aspose.words/range/structureddocumenttags/) { get; } | Bir döndürür[`StructuredDocumentTags`](./structureddocumenttags/) aralığındaki tüm yapılandırılmış belge etiketlerini temsil eden koleksiyon. |
| [Text](../../aspose.words/range/text/) { get; } | Aralığın metnini alır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Delete](../../aspose.words/range/delete/)() | Aralığın tüm karakterlerini siler. |
| [NormalizeFieldTypes](../../aspose.words/range/normalizefieldtypes/)() | Alan türü değerlerini değiştirir[`FieldType`](../../aspose.words.fields/fieldchar/fieldtype/) nın-nin[`FieldStart`](../../aspose.words.fields/fieldstart/) ,[`FieldSeparator`](../../aspose.words.fields/fieldseparator/) ,[`FieldEnd`](../../aspose.words.fields/fieldend/) alan kodlarında yer alan alan türlerine karşılık gelecek şekilde bu aralıkta. |
| [Replace](../../aspose.words/range/replace/#replace_2)(Regex, string) | Normal bir ifadeyle belirtilen bir karakter deseninin tüm oluşumlarını başka bir dizeyle değiştirir. |
| [Replace](../../aspose.words/range/replace/#replace)(string, string) | Belirtilen karakter dizesi modelinin tüm oluşumlarını bir yedek dizeyle değiştirir. |
| [Replace](../../aspose.words/range/replace/#replace_3)(Regex, string, FindReplaceOptions) | Normal bir ifadeyle belirtilen bir karakter deseninin tüm oluşumlarını başka bir dizeyle değiştirir. |
| [Replace](../../aspose.words/range/replace/#replace_1)(string, string, FindReplaceOptions) | Belirtilen karakter dizesi modelinin tüm oluşumlarını bir yedek dizeyle değiştirir. |
| [ToDocument](../../aspose.words/range/todocument/)() | Aralığı içeren tam biçimli yeni bir belge oluşturur. |
| [UnlinkFields](../../aspose.words/range/unlinkfields/)() | Bu aralıktaki alanların bağlantısını kaldırır. |
| [UpdateFields](../../aspose.words/range/updatefields/)() | Bu aralıktaki belge alanlarının değerlerini günceller. |

### Notlar

Belge, bir düğüm ağacı ile temsil edilir ve düğümler, ağaçla çalışmak için operasyonlar sağlar, ancak belge , bitişik bir metin dizisi olarak ele alınırsa, bazı işlemlerin gerçekleştirilmesi daha kolaydır.

**Menzil** Document düğümlerinin ağaç benzeri bir nesne modelinde depolanmış olmasına bakılmaksızın, document veya belgenin bölümlerini "düz" metin olarak ele alan yöntemler sağlayan bir "cephe" arabirimidir.

**Menzil** herhangi bir metin veya düğüm içermez, yalnızca bir belgenin bir parçası üzerindeki bir görünüm veya "pencere" 'dir.

### Örnekler

Bir aralığın kapsadığı tüm düğümlerin metin içeriğinin nasıl alınacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");

Assert.AreEqual("Hello world!", doc.Range.Text.Trim());
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


