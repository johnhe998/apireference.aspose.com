---
title: FieldToc.UpdatePageNumbers
second_title: Aspose.Words for .NET API Referansı
description: FieldToc yöntem. Bu içindekiler tablosundaki öğelerin sayfa numaralarını günceller.
type: docs
weight: 180
url: /tr/net/aspose.words.fields/fieldtoc/updatepagenumbers/
---
## FieldToc.UpdatePageNumbers method

Bu içindekiler tablosundaki öğelerin sayfa numaralarını günceller.

```csharp
public bool UpdatePageNumbers()
```

### Geri dönüş değeri

İşlem başarılıysa doğrudur. İlgili TOC yer işaretlerinden herhangi biri kaldırıldıysa false döndürülür.

### Örnekler

İçindekiler'in nasıl ekleneceğini ve başlık stillerine göre girişlerle nasıl doldurulacağını gösterir.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("MyBookmark");

    // Tüm başlıkları bir içindekiler tablosunda derleyecek bir TOC alanı ekleyin.
    // Her başlık için bu alan, soldaki o başlık stilindeki metinle birlikte bir satır oluşturacaktır,
    // ve başlığın sağda göründüğü sayfa.
    FieldToc field = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

    // Yalnızca başlıkları listelemek için BookmarkName özelliğini kullanın
    // "MyBookmark" adıyla bir yer iminin sınırları içinde görünen.
    field.BookmarkName = "MyBookmark";

    // "Başlık 1" gibi yerleşik bir başlık stiline sahip metinler, başlık olarak sayılır.
    // Bu özellikte TOC tarafından başlık olarak alınacak ek stilleri ve TOC seviyelerini adlandırabiliriz.
    field.CustomStyles = "Quote; 6; Intense Quote; 7";

    // Varsayılan olarak, Styles/TOC seviyeleri CustomStyles özelliğinde virgülle ayrılır,
    // ancak bu özellikte özel bir sınırlayıcı ayarlayabiliriz.
    doc.FieldOptions.CustomTocStyleSeparator = ";";

    // Bu aralığın dışında TOC düzeylerine sahip tüm başlıkları hariç tutmak için alanı yapılandırın.
    field.HeadingLevelRange = "1-3";

    // İçindekiler, TOC seviyeleri bu aralıkta olan başlıkların sayfa numaralarını göstermeyecektir.
    field.PageNumberOmittingLevelRange = "2-5";

     // Her başlığı sayfa numarasından ayıracak özel bir dize ayarlayın.
    field.EntrySeparator = "-";
    field.InsertHyperlinks = true;
    field.HideInWebLayout = false;
    field.PreserveLineBreaks = true;
    field.PreserveTabs = true;
    field.UseParagraphOutlineLevel = false;

    InsertNewPageWithHeading(builder, "First entry", "Heading 1");
    builder.Writeln("Paragraph text.");
    InsertNewPageWithHeading(builder, "Second entry", "Heading 1");
    InsertNewPageWithHeading(builder, "Third entry", "Quote");
    InsertNewPageWithHeading(builder, "Fourth entry", "Intense Quote");

    // Bu iki başlık, "2-5" aralığında oldukları için sayfa numaralarına sahip olmayacaktır.
    InsertNewPageWithHeading(builder, "Fifth entry", "Heading 2");
    InsertNewPageWithHeading(builder, "Sixth entry", "Heading 3");

    // "Başlık 4", daha önce belirlediğimiz "1-3" aralığının dışında olduğu için bu giriş görünmüyor.
    InsertNewPageWithHeading(builder, "Seventh entry", "Heading 4");

    builder.EndBookmark("MyBookmark");
    builder.Writeln("Paragraph text.");

    // Bu girdi, İçindekiler tarafından belirtilen yer iminin dışında olduğu için görünmüyor.
    InsertNewPageWithHeading(builder, "Eighth entry", "Heading 1");

    Assert.AreEqual(" TOC  \\b MyBookmark \\t \"Quote; 6; Intense Quote; 7\" \\o 1-3 \\n 2-5 \\p - \\h \\x \\w", field.GetFieldCode());

    field.UpdatePageNumbers();
    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.TOC.docx");

/// <summary>
/// Yeni bir sayfa başlatın ve belirtilen stilde bir paragraf ekleyin.
/// </summary>
public void InsertNewPageWithHeading(DocumentBuilder builder, string captionText, string styleName)
{
    builder.InsertBreak(BreakType.PageBreak);
    string originalStyle = builder.ParagraphFormat.StyleName;
    builder.ParagraphFormat.Style = builder.Document.Styles[styleName];
    builder.Writeln(captionText);
    builder.ParagraphFormat.Style = builder.Document.Styles[originalStyle];
}
```

### Ayrıca bakınız

* class [FieldToc](../)
* ad alanı [Aspose.Words.Fields](../../fieldtoc/)
* toplantı [Aspose.Words](../../../)


