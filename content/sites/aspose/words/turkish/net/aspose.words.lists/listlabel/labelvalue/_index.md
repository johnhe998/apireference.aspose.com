---
title: ListLabel.LabelValue
second_title: Aspose.Words for .NET API Referansı
description: ListLabel mülk. Bu etiket için sayısal bir değer alır.
type: docs
weight: 30
url: /tr/net/aspose.words.lists/listlabel/labelvalue/
---
## ListLabel.LabelValue property

Bu etiket için sayısal bir değer alır.

```csharp
public int LabelValue { get; }
```

### Notlar

[`UpdateListLabels`](../../../aspose.words/document/updatelistlabels/) bu özelliğin değerini güncelleme yöntemi.

### Örnekler

Liste öğeleri olan tüm paragrafların liste etiketlerinin nasıl çıkarılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
doc.UpdateListLabels();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

// Paragraf listesine sahip olup olmadığımızı bulun. Belgemizde listemizde düz Arapça sayılar kullanılıyor,
// üçte başlayan ve altıda biten.
foreach (Paragraph paragraph in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{
    Console.WriteLine($"List item paragraph #{paras.IndexOf(paragraph)}");

    // Bu düğümü metin biçimine çıkardığımızda aldığımız metin budur.
    // Bu metin çıktısı liste etiketlerini atlayacak. Paragraf biçimlendirme karakterlerini kırpın. 
    string paragraphText = paragraph.ToString(SaveFormat.Text).Trim();
    Console.WriteLine($"\tExported Text: {paragraphText}");

    ListLabel label = paragraph.ListLabel;

    // Bu, listenin geçerli düzeyinde paragrafın konumunu alır. Birden fazla seviye içeren bir listemiz varsa,
    // bu bize o seviyede hangi pozisyonda olduğunu söyleyecek.
    Console.WriteLine($"\tNumerical Id: {label.LabelValue}");

    // Çıktıdaki metinle liste etiketini dahil etmek için bunları birleştirin.
    Console.WriteLine($"\tList label combined with text: {label.LabelString} {paragraphText}");
}
```

### Ayrıca bakınız

* class [ListLabel](../)
* ad alanı [Aspose.Words.Lists](../../listlabel/)
* toplantı [Aspose.Words](../../../)


