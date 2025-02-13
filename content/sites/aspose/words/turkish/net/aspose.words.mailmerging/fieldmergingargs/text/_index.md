---
title: FieldMergingArgs.Text
second_title: Aspose.Words for .NET API Referansı
description: FieldMergingArgs mülk. Geçerli birleştirme alanı için belgeye eklenecek metni alır veya ayarlar.
type: docs
weight: 10
url: /tr/net/aspose.words.mailmerging/fieldmergingargs/text/
---
## FieldMergingArgs.Text property

Geçerli birleştirme alanı için belgeye eklenecek metni alır veya ayarlar.

```csharp
public string Text { get; set; }
```

### Notlar

Olay işleyiciniz çağrıldığında bu özellik null olarak ayarlanır.

Metni boş bırakırsanız, adres mektup birleştirme motoru[`FieldValue`](../../fieldmergingargsbase/fieldvalue/) birleştirme alanı yerine.

Metni herhangi bir dizeye (boş dahil) ayarlarsanız, dize, birleştirme alanının yerine belgeye eklenir.

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

* class [FieldMergingArgs](../)
* ad alanı [Aspose.Words.MailMerging](../../fieldmergingargs/)
* toplantı [Aspose.Words](../../../)


