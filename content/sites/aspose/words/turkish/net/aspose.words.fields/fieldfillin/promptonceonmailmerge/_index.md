---
title: FieldFillIn.PromptOnceOnMailMerge
second_title: Aspose.Words for .NET API Referansı
description: FieldFillIn mülk. Bir adres mektup birleştirme işlemi başına kullanıcı yanıtının bir kez alınıp alınmayacağını alır veya ayarlar.
type: docs
weight: 30
url: /tr/net/aspose.words.fields/fieldfillin/promptonceonmailmerge/
---
## FieldFillIn.PromptOnceOnMailMerge property

Bir adres mektup birleştirme işlemi başına kullanıcı yanıtının bir kez alınıp alınmayacağını alır veya ayarlar.

```csharp
public bool PromptOnceOnMailMerge { get; set; }
```

### Örnekler

Kullanıcıdan bir yanıt istemek için DOLDURMA alanının nasıl kullanılacağını gösterir.

```csharp
public void FieldFillIn()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Bir FILLIN alanı ekleyin. Bu alanı Microsoft Word'de manuel olarak güncellediğimizde,
    // bir yanıt girmemizi isteyecek. Alan daha sonra yanıtı metin olarak görüntüler.
    FieldFillIn field = (FieldFillIn)builder.InsertField(FieldType.FieldFillIn, true);
    field.PromptText = "Please enter a response:";
    field.DefaultResponse = "A default response.";

    // Bu alanları, kullanıcıdan her sayfa için benzersiz bir yanıt istemek için de kullanabiliriz.
    // Microsoft Word kullanılarak yapılan adres mektup birleştirme sırasında oluşturuldu.
    field.PromptOnceOnMailMerge = true;

    Assert.AreEqual(" FILLIN  \"Please enter a response:\" \\d \"A default response.\" \\o", field.GetFieldCode());

    FieldMergeField mergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
    mergeField.FieldName = "MergeField";

    // Programlı olarak adres mektup birleştirme gerçekleştirirsek, özel bir istem yanıtlayıcı kullanabiliriz
    // adres mektup birleştirmenin karşılaştığı FILLIN alanlarına yönelik yanıtları otomatik olarak düzenlemek için.
    doc.FieldOptions.UserPromptRespondent = new PromptRespondent();
    doc.MailMerge.Execute(new [] { "MergeField" }, new object[] { "" });

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.FILLIN.docx");

/// <summary>
/// Adres mektup birleştirme sırasında her FILLIN alanının varsayılan yanıtının başına bir satır ekler.
/// </summary>
private class PromptRespondent : IFieldUserPromptRespondent
{
    public string Respond(string promptText, string defaultResponse)
    {
        return "Response modified by PromptRespondent. " + defaultResponse;
    }
}
```

### Ayrıca bakınız

* class [FieldFillIn](../)
* ad alanı [Aspose.Words.Fields](../../fieldfillin/)
* toplantı [Aspose.Words](../../../)


