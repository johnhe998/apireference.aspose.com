---
title: Class FieldMergingArgs
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.MailMerging.FieldMergingArgs sınıf. için veri sağlar Birleştirme Alanı olay.
type: docs
weight: 3550
url: /tr/net/aspose.words.mailmerging/fieldmergingargs/
---
## FieldMergingArgs class

için veri sağlar **Birleştirme Alanı** olay.

```csharp
public class FieldMergingArgs : FieldMergingArgsBase
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Document](../../aspose.words.mailmerging/fieldmergingargsbase/document/) { get; } | [`Document`](../fieldmergingargsbase/document/) adres mektup birleştirmenin gerçekleştirildiği nesne. |
| [DocumentFieldName](../../aspose.words.mailmerging/fieldmergingargsbase/documentfieldname/) { get; } | Belgede belirtildiği gibi birleştirme alanının adını alır. |
| [Field](../../aspose.words.mailmerging/fieldmergingargsbase/field/) { get; } | Geçerli birleştirme alanını temsil eden nesneyi alır. |
| [FieldName](../../aspose.words.mailmerging/fieldmergingargsbase/fieldname/) { get; } | Veri kaynağındaki birleştirme alanının adını alır. |
| [FieldValue](../../aspose.words.mailmerging/fieldmergingargsbase/fieldvalue/) { get; set; } | Veri kaynağından alanın değerini alır veya ayarlar. |
| [RecordIndex](../../aspose.words.mailmerging/fieldmergingargsbase/recordindex/) { get; } | Birleştirilmekte olan kaydın sıfır tabanlı dizinini alır. |
| [TableName](../../aspose.words.mailmerging/fieldmergingargsbase/tablename/) { get; } | Geçerli birleştirme işlemi için veri tablosunun adını veya ad yoksa boş dize adını alır. |
| [Text](../../aspose.words.mailmerging/fieldmergingargs/text/) { get; set; } | Geçerli birleştirme alanı için belgeye eklenecek metni alır veya ayarlar. |

### Notlar

bu **Birleştirme Alanı** olay, adres mektup birleştirme sırasında belgede basit bir adres mektup birleştirme alanıyla karşılaşıldığında oluşur. Adres mektup birleştirme motorunun belgeye eklemesi için bu olaya return metnini yanıtlayabilirsiniz.

### Örnekler

Birleştirme verilerini HTML belgeleri biçiminde işleyen özel bir geri aramayla adres mektup birleştirmenin nasıl yürütüleceğini gösterir.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(@"MERGEFIELD  html_Title  \b Content");
    builder.InsertField(@"MERGEFIELD  html_Body  \b Content");

    object[] mergeData =
    {
        "<html>" +
            "<h1>" +
                "<span style=\"color: #0000ff; font-family: Arial;\">Hello World!</span>" +
            "</h1>" +
        "</html>", 

        "<html>" +
            "<blockquote>" +
                "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>" +
            "</blockquote>" +
        "</html>"
    };

    doc.MailMerge.FieldMergingCallback = new HandleMergeFieldInsertHtml();
    doc.MailMerge.Execute(new[] { "html_Title", "html_Body" }, mergeData);

    doc.Save(ArtifactsDir + "MailMergeEvent.MergeHtml.docx");
}

/// <summary>
/// Adres mektup birleştirme, adı "html_" öneki ile başlayan bir MERGEFIELD ile karşılaşırsa,
/// bu geri arama, birleştirme verilerini HTML içeriği olarak ayrıştırır ve sonucu MERGEFIELD'in belge konumuna ekler.
/// </summary>
private class HandleMergeFieldInsertHtml : IFieldMergingCallback
{
    /// <summary>
    /// Adres mektup birleştirme verileri bir MERGEFIELD ile birleştirdiğinde çağrılır.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName.StartsWith("html_") && args.Field.GetFieldCode().Contains("\\b"))
        {
            // Ayrıştırılmış HTML verilerini belgenin gövdesine ekleyin.
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);
            builder.InsertHtml((string)args.FieldValue);

            // Birleştirilmiş içeriği zaten manuel olarak eklediğimiz için,
             // "Metin" özelliği aracılığıyla içerik döndürerek bu olaya yanıt vermemiz gerekmeyecek.
            args.Text = string.Empty;
        }
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs args)
    {
        // Hiçbir şey yapma.
    }
}
```

### Ayrıca bakınız

* class [FieldMergingArgsBase](../fieldmergingargsbase/)
* ad alanı [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* toplantı [Aspose.Words](../../)


