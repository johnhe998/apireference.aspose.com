---
title: FieldAutoNumLgl.SeparatorCharacter
second_title: Aspose.Words for .NET API Referansı
description: FieldAutoNumLgl mülk. Kullanılacak ayırıcı karakteri alır veya ayarlar.
type: docs
weight: 30
url: /tr/net/aspose.words.fields/fieldautonumlgl/separatorcharacter/
---
## FieldAutoNumLgl.SeparatorCharacter property

Kullanılacak ayırıcı karakteri alır veya ayarlar.

```csharp
public string SeparatorCharacter { get; set; }
```

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

* class [FieldAutoNumLgl](../)
* ad alanı [Aspose.Words.Fields](../../fieldautonumlgl/)
* toplantı [Aspose.Words](../../../)


