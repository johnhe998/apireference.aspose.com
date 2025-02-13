---
title: Class FieldAutoNumLgl
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fields.FieldAutoNumLgl sınıf. AUTONUMLGL alanını uygular.
type: docs
weight: 1440
url: /tr/net/aspose.words.fields/fieldautonumlgl/
---
## FieldAutoNumLgl class

AUTONUMLGL alanını uygular.

```csharp
public class FieldAutoNumLgl : Field
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [FieldAutoNumLgl](fieldautonumlgl/)() | Default_Constructor |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | Görüntülenen alan sonucunu temsil eden metni alır. |
| [End](../../aspose.words.fields/field/end/) { get; } | Alan sonunu temsil eden düğümü alır. |
| [Format](../../aspose.words.fields/field/format/) { get; } | [`FieldFormat`](../fieldformat/) alanın biçimlendirmesine yazılı erişim sağlayan nesne. |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | Belgede yapılan diğer değişiklikler nedeniyle alanın geçerli sonucunun artık doğru (eski) olup olmadığını alır veya ayarlar. |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | Alanın kilitli olup olmadığını alır veya ayarlar (sonucunu yeniden hesaplamamalıdır). |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | Alanın LCID'sini alır veya ayarlar. |
| [RemoveTrailingPeriod](../../aspose.words.fields/fieldautonumlgl/removetrailingperiod/) { get; set; } | Sayının sonunda nokta olmadan görüntülenip görüntülenmeyeceğini alır veya ayarlar. |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | Alan ayırıcı ile alan sonu arasındaki metni alır veya ayarlar. |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | Alan ayırıcıyı temsil eden düğümü alır. null. olabilir |
| [SeparatorCharacter](../../aspose.words.fields/fieldautonumlgl/separatorcharacter/) { get; set; } | Kullanılacak ayırıcı karakteri alır veya ayarlar. |
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

### Notlar

Yasal biçimde otomatik bir numara ekler.

### Örnekler

AUTONUMLGL alanlarını kullanarak bir belgenin nasıl düzenleneceğini gösterir.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    const string fillerText = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
                              "\nUt enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ";

    // AUTONUMLGL alanları, mevcut başlık düzeyinde her AUTONUMLGL alanında artan bir sayı görüntüler.
    // Bu alanlar, her başlık seviyesi için ayrı bir sayı tutar,
     // ve her alan, kendi altındaki tüm başlık seviyeleri için AUTONUMLGL alan sayılarını da görüntüler.
    // Herhangi bir başlık seviyesi için sayıyı değiştirmek, o seviyenin üzerindeki tüm seviyeler için sayıları 1'e sıfırlar.
    // Bu, belgemizi bir anahat listesi şeklinde düzenlememizi sağlar.
    // Bu, 1 başlık düzeyindeki ilk AUTONUMLGL alanıdır ve "1" gösterir. belgede.
    InsertNumberedClause(builder, "\tHeading 1", fillerText, StyleIdentifier.Heading1);

    // Bu, 1 başlık seviyesindeki ikinci AUTONUMLGL alanıdır, bu nedenle "2" gösterecektir.
    InsertNumberedClause(builder, "\tHeading 2", fillerText, StyleIdentifier.Heading1);

    // Bu, 2 başlık seviyesindeki ilk AUTONUMLGL alanıdır,
    // ve altındaki başlık seviyesi için AUTONUMLGL sayısı "2" olduğundan "2.1" görüntülenecektir.
    InsertNumberedClause(builder, "\tHeading 3", fillerText, StyleIdentifier.Heading2);

     // Bu, 3 başlık seviyesindeki ilk AUTONUMLGL alanıdır.
    // Yukarıdaki alanla aynı şekilde çalışarak "2.1.1." gösterecektir.
    InsertNumberedClause(builder, "\tHeading 4", fillerText, StyleIdentifier.Heading3);

    // Bu alan 2 başlık seviyesindedir ve ilgili AUTONUMLGL sayısı 2'dedir, bu nedenle alan "2.2." görüntüleyecektir.
    InsertNumberedClause(builder, "\tHeading 5", fillerText, StyleIdentifier.Heading2);

    // Bunun altındaki bir başlık seviyesi için AUTONUMLGL sayısını artırma
    // bu alan "2.2.1." gösterecek şekilde bu seviye için sayımı sıfırladı.
    InsertNumberedClause(builder, "\tHeading 6", fillerText, StyleIdentifier.Heading3);

    foreach (FieldAutoNumLgl field in doc.Range.Fields.Where(f => f.Type == FieldType.FieldAutoNumLegal))
    {
        // Sayıdan hemen sonra sonuç alanında görünen ayırıcı karakter,
        // varsayılan olarak bir noktadır. Bu özelliği boş bırakırsak,
        // son AUTONUMLGL alanımız "2.2.1" gösterecek. belgede.
        Assert.IsNull(field.SeparatorCharacter);

        // Özel bir ayırıcı karakter ayarlama ve sondaki noktayı kaldırma
        // bu alanın görünümünü "2.2.1"den değiştirecek. "2:2:1"e kadar.
        // Oluşturduğumuz tüm alanlara bunu uygulayacağız.
        field.SeparatorCharacter = ":";
        field.RemoveTrailingPeriod = true;
        Assert.AreEqual(" AUTONUMLGL  \\s : \\e", field.GetFieldCode());
    }

    doc.Save(ArtifactsDir + "Field.AUTONUMLGL.docx");

/// <summary>
/// AUTONUMLGL alanıyla numaralandırılmış bir yan tümce eklemek için bir belge oluşturucu kullanır.
/// </summary>
private static void InsertNumberedClause(DocumentBuilder builder, string heading, string contents, StyleIdentifier headingStyle)
{
    builder.InsertField(FieldType.FieldAutoNumLegal, true);
    builder.CurrentParagraph.ParagraphFormat.StyleIdentifier = headingStyle;
    builder.Writeln(heading);

    // Bu metin, üstündeki auto num legal alanına ait olacaktır.
    // Microsoft Word'de ilgili AUTONUMLGL alanının yanındaki oka tıkladığımızda çökecektir.
    builder.CurrentParagraph.ParagraphFormat.StyleIdentifier = StyleIdentifier.BodyText;
    builder.Writeln(contents);
}
```

### Ayrıca bakınız

* class [Field](../field/)
* ad alanı [Aspose.Words.Fields](../../aspose.words.fields/)
* toplantı [Aspose.Words](../../)


