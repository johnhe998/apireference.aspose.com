---
title: Class FieldEmbed
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fields.FieldEmbed sınıf. EMBED alanını uygular.
type: docs
weight: 1700
url: /tr/net/aspose.words.fields/fieldembed/
---
## FieldEmbed class

EMBED alanını uygular.

```csharp
public class FieldEmbed : Field
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [FieldEmbed](fieldembed/)() | Default_Constructor |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | Görüntülenen alan sonucunu temsil eden metni alır. |
| [End](../../aspose.words.fields/field/end/) { get; } | Alan sonunu temsil eden düğümü alır. |
| [Format](../../aspose.words.fields/field/format/) { get; } | [`FieldFormat`](../fieldformat/) alanın biçimlendirmesine yazılı erişim sağlayan nesne. |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | Belgede yapılan diğer değişiklikler nedeniyle alanın geçerli sonucunun artık doğru (eski) olup olmadığını alır veya ayarlar. |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | Alanın kilitli olup olmadığını alır veya ayarlar (sonucunu yeniden hesaplamamalıdır). |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | Alanın LCID'sini alır veya ayarlar. |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | Alan ayırıcı ile alan sonu arasındaki metni alır veya ayarlar. |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | Alan ayırıcıyı temsil eden düğümü alır. null. olabilir |
| [Start](../../aspose.words.fields/field/start/) { get; } | Alanın başlangıcını temsil eden düğümü alır. |
| virtual [Type](../../aspose.words.fields/field/type/) { get; } | Microsoft Word alan türünü alır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)() | Alan başlangıcı ile alan ayırıcı (veya ayırıcı yoksa alan sonu) arasındaki metni döndürür. Alt alanların hem alan kodu hem de alan sonucu dahil edilir. |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)(bool) | Alan başlangıcı ile alan ayırıcı (veya ayırıcı yoksa alan sonu) arasındaki metni döndürür. |
| [Remove](../../aspose.words.fields/field/remove/)() | Alanı belgeden kaldırır. Alandan hemen sonra bir düğüm döndürür. Alanın sonu, üst düğümünün son çocuğu ise, üst paragrafını döndürür. Alan zaten kaldırılmışsa, döner **hükümsüz** . |
| [Unlink](../../aspose.words.fields/field/unlink/)() | Bağlantıyı kaldır alanını gerçekleştirir. |
| [Update](../../aspose.words.fields/field/update/)() | Alan güncellemesini gerçekleştirir. Alan zaten güncelleniyorsa atar. |
| [Update](../../aspose.words.fields/field/update/)(bool) | Bir alan güncellemesi gerçekleştirir. Alan zaten güncelleniyorsa atar. |

### Örnekler

SHAPE ve EMBED gibi bazı eski Microsoft Word alanlarının yükleme sırasında nasıl işlendiğini gösterir.

```csharp
// Microsoft Word 2003'te oluşturulmuş bir belgeyi açın.
Document doc = new Document(MyDir + "Legacy fields.doc");

// Word belgesini açıp Alt+F9'a basarsak bir SHAPE ve EMBED alanı göreceğiz.
// SHAPE alanı, "Metinle uyumlu" kaydırma stili etkinleştirilmiş bir Otomatik Şekil nesnesi için bağlantı/tuvaldir.
// Bir EMBED alanı aynı işleve sahiptir, ancak gömülü bir nesne için,
// harici bir Excel belgesinden bir elektronik tablo gibi.
// Ancak bu alanlar belgenin Fields koleksiyonunda görünmez.
Assert.AreEqual(0, doc.Range.Fields.Count);

// Bu alanlar yalnızca Microsoft Word'ün eski sürümleri tarafından desteklenir.
// Belge yükleme işlemi bu alanları Shape nesnelerine dönüştürecek,
// belgenin düğüm koleksiyonundan erişebileceğimiz.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);
Assert.AreEqual(3, shapes.Count);

// İlk Shape düğümü, giriş belgesindeki SHAPE alanına karşılık gelir,
// Otomatik Şekil için satır içi tuval.
Shape shape = (Shape)shapes[0];
Assert.AreEqual(ShapeType.Image, shape.ShapeType);

// İkinci Şekil düğümü, Otomatik Şekil'in kendisidir.
shape = (Shape)shapes[1];
Assert.AreEqual(ShapeType.Can, shape.ShapeType);

// Üçüncü Şekil, harici elektronik tabloyu içeren EMBED alanıdır.
shape = (Shape)shapes[2];
Assert.AreEqual(ShapeType.OleObject, shape.ShapeType);
```

### Ayrıca bakınız

* class [Field](../field/)
* ad alanı [Aspose.Words.Fields](../../aspose.words.fields/)
* toplantı [Aspose.Words](../../)


