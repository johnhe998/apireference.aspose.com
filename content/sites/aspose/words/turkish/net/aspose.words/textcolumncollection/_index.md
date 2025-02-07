---
title: Class TextColumnCollection
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.TextColumnCollection sınıf. Bir koleksiyonTextColumn bir belgenin bir bölümündeki metnin tüm sütunlarını temsil eden nesneler.
type: docs
weight: 6100
url: /tr/net/aspose.words/textcolumncollection/
---
## TextColumnCollection class

Bir koleksiyon[`TextColumn`](../textcolumn/) bir belgenin bir bölümündeki metnin tüm sütunlarını temsil eden nesneler.

```csharp
public class TextColumnCollection
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words/textcolumncollection/count/) { get; } | Bir belgenin bölümündeki sütun sayısını alır. |
| [EvenlySpaced](../../aspose.words/textcolumncollection/evenlyspaced/) { get; set; } | **Doğru** metin sütunları eşit genişlikte ve eşit aralıklıysa. |
| [Item](../../aspose.words/textcolumncollection/item/) { get; } | Belirtilen dizinde bir metin sütunu döndürür. |
| [LineBetween](../../aspose.words/textcolumncollection/linebetween/) { get; set; } | Ne zaman **doğru** , sütunlar arasına dikey bir çizgi ekler. |
| [Spacing](../../aspose.words/textcolumncollection/spacing/) { get; set; } | Sütunlar eşit aralıklarla yerleştirildiğinde, her sütun arasındaki boşluk miktarını nokta olarak alır veya ayarlar. |
| [Width](../../aspose.words/textcolumncollection/width/) { get; } | Sütunlar eşit aralıklarla yerleştirildiğinde, sütunların genişliğini alır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [SetCount](../../aspose.words/textcolumncollection/setcount/)(int) | Metni belirtilen sayıda metin sütununa göre düzenler. |

### Notlar

Kullanmak[`SetCount`](./setcount/) metin sütunlarının sayısını ayarlamak için

Tüm sütunları eşit genişlikte ve eşit aralıklı yapmak için[`EvenlySpaced`](./evenlyspaced/) ile **doğru** ve içindeki sütunlar arasındaki boşluk miktarını belirtin[`Spacing`](./spacing/). MS Word sütun genişliklerini otomatik olarak hesaplayacaktır.

eğer varsa **Eşit Aralıklı** ayarlanır **yanlış** her bir sütunu için ayrı ayrı genişlik ve boşluk belirtmeniz gerekir. Bireye erişmek için dizin oluşturucuyu kullanın[`TextColumn`](../textcolumn/) nesneler.

Özel sütun genişliklerini kullanırken, tüm sütun genişliklerinin ve bunlar arasındaki boşlukların toplamının, sayfa genişliği eksi sol ve sağ sayfa kenar boşluklarına eşit olduğundan emin olun.

### Örnekler

Bir bölümde birden çok eşit aralıklı sütunun nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


