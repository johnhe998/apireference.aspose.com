---
title: FieldPageRef.InsertRelativePosition
second_title: Aspose.Words for .NET API Referansı
description: FieldPageRef mülk. Yer işaretli paragrafın göreli konumunun eklenip eklenmeyeceğini alır veya ayarlar.
type: docs
weight: 40
url: /tr/net/aspose.words.fields/fieldpageref/insertrelativeposition/
---
## FieldPageRef.InsertRelativePosition property

Yer işaretli paragrafın göreli konumunun eklenip eklenmeyeceğini alır veya ayarlar.

```csharp
public bool InsertRelativePosition { get; set; }
```

### Örnekler

Yer imlerinin göreli konumunu görüntülemek için PAGEREF alanları eklemeyi gösterir.

```csharp
public void FieldPageRef()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    InsertAndNameBookmark(builder, "MyBookmark1");

    // Yer iminin hangi sayfada olduğunu gösteren bir PAGEREF alanı ekleyin.
    // Alanın aynı zamanda yer işaretine tıklanabilir bir bağlantı olarak işlev görmesini sağlamak için InsertHyperlink bayrağını ayarlayın.
    Assert.AreEqual(" PAGEREF  MyBookmark3 \\h", 
        InsertFieldPageRef(builder, "MyBookmark3", true, false, "Hyperlink to Bookmark3, on page: ").GetFieldCode());

    // PAGEREF alanını görüntülemek için \p bayrağını kullanabiliriz
    // yer iminin alanın konumuna göre konumu.
    // Bookmark1 aynı sayfada ve bu alanın üstünde olduğundan, bu alanın görüntülenen sonucu "yukarıda" olacaktır.
    Assert.AreEqual(" PAGEREF  MyBookmark1 \\h \\p", 
        InsertFieldPageRef(builder, "MyBookmark1", true, true, "Bookmark1 is ").GetFieldCode());

    // Bookmark2 aynı sayfada ve bu alanın altında olacak, bu nedenle bu alanın görüntülenen sonucu "aşağıda" olacaktır.
    Assert.AreEqual(" PAGEREF  MyBookmark2 \\h \\p", 
        InsertFieldPageRef(builder, "MyBookmark2", true, true, "Bookmark2 is ").GetFieldCode());

    // Bookmark3 farklı bir sayfada olacak, bu yüzden alan "sayfa 2'de" görüntülenecektir.
    Assert.AreEqual(" PAGEREF  MyBookmark3 \\h \\p", 
        InsertFieldPageRef(builder, "MyBookmark3", true, true, "Bookmark3 is ").GetFieldCode());

    InsertAndNameBookmark(builder, "MyBookmark2");
    builder.InsertBreak(BreakType.PageBreak);
    InsertAndNameBookmark(builder, "MyBookmark3");

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.PAGEREF.docx");

/// <summary>
/// Bir PAGEREF alanı eklemek için bir belge oluşturucu kullanır ve özelliklerini ayarlar.
/// </summary>
private static FieldPageRef InsertFieldPageRef(DocumentBuilder builder, string bookmarkName, bool insertHyperlink, bool insertRelativePosition, string textBefore)
{
    builder.Write(textBefore);

    FieldPageRef field = (FieldPageRef)builder.InsertField(FieldType.FieldPageRef, true);
    field.BookmarkName = bookmarkName;
    field.InsertHyperlink = insertHyperlink;
    field.InsertRelativePosition = insertRelativePosition;
    builder.Writeln();

    return field;
}

/// <summary>
/// Adlandırılmış bir yer imi eklemek için bir belge oluşturucu kullanır.
/// </summary>
private static void InsertAndNameBookmark(DocumentBuilder builder, string bookmarkName)
{
    builder.StartBookmark(bookmarkName);
    builder.Writeln($"Contents of bookmark \"{bookmarkName}\".");
    builder.EndBookmark(bookmarkName);
}
```

### Ayrıca bakınız

* class [FieldPageRef](../)
* ad alanı [Aspose.Words.Fields](../../fieldpageref/)
* toplantı [Aspose.Words](../../../)


