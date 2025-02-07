---
title: Document.UpdateListLabels
second_title: Aspose.Words for .NET API Referansı
description: Document yöntem. Belgedeki tüm liste öğeleri için liste etiketlerini günceller.
type: docs
weight: 740
url: /tr/net/aspose.words/document/updatelistlabels/
---
## Document.UpdateListLabels method

Belgedeki tüm liste öğeleri için liste etiketlerini günceller.

```csharp
public void UpdateListLabels()
```

### Notlar

Bu yöntem, aşağıdakiler gibi liste etiketi özelliklerini günceller:[`LabelValue`](../../../aspose.words.lists/listlabel/labelvalue/) and [`LabelString`](../../../aspose.words.lists/listlabel/labelstring/)her biri için[`ListLabel`](../../paragraph/listlabel/) belgedeki nesne.

Ayrıca, bu yöntem bazen belgedeki alanlar güncellenirken örtük olarak çağrılır. Bu gereklidir çünkü liste numaralarına (TOC veya REF gibi) başvurabilecek bazı alanların güncel olmaları gerekir.

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

* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


