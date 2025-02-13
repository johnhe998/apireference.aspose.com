---
title: LayoutCollector.Document
second_title: Aspose.Words for .NET API Referansı
description: LayoutCollector mülk. Bu toplayıcı örneğinin eklendiği belgeyi alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.layout/layoutcollector/document/
---
## LayoutCollector.Document property

Bu toplayıcı örneğinin eklendiği belgeyi alır veya ayarlar.

```csharp
public Document Document { get; set; }
```

### Notlar

Belge düğümlerinin sayfa dizinlerine erişmeniz gerekiyorsa, bu özelliği, belgenin sayfa düzeni oluşturulmadan önce bir belge örneğini, işaret edecek şekilde ayarlamanız gerekir. Bu özelliği ayarlamak en iyisidir`hükümsüz`ardından, aksi takdirde toplayıcı, belgenin sayfa düzeninin sonraki yeniden oluşturma işlemlerinden bilgi toplamaya devam eder.

### Örnekler

Bir düğümün yaydığı sayfa aralıklarının nasıl görüneceğini gösterir.

```csharp
Document doc = new Document();
LayoutCollector layoutCollector = new LayoutCollector(doc);

// Belgemizin içeriğinin kaç sayfaya yayıldığını saymak için "GetNumPagesSpanned" yöntemini çağırın.
// Belge boş olduğundan, o sayfa sayısı şu anda sıfırdır.
Assert.AreEqual(doc, layoutCollector.Document);
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

// Belgeyi 5 sayfa içerikle doldurun.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Section 1");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);

// layout toplayıcıdan önce bize verecek "UpdatePageLayout" yöntemini çağırmamız gerekiyor.
// sayfa sayısı gibi mizanpajla ilgili herhangi bir ölçüm için doğru bir rakam.
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

layoutCollector.Clear();
doc.UpdatePageLayout();

Assert.AreEqual(5, layoutCollector.GetNumPagesSpanned(doc));

// Herhangi bir düğümün başlangıç ve bitiş sayfalarının numaralarını ve bunların genel sayfa aralıklarını görebiliriz.
NodeCollection nodes = doc.GetChildNodes(NodeType.Any, true);
foreach (Node node in nodes)
{
    Console.WriteLine($"->  NodeType.{node.NodeType}: ");
    Console.WriteLine(
        $"\tStarts on page {layoutCollector.GetStartPageIndex(node)}, ends on page {layoutCollector.GetEndPageIndex(node)}," +
        $" spanning {layoutCollector.GetNumPagesSpanned(node)} pages.");
}

// Bir LayoutEnumerator kullanarak düzen varlıklarını yineleyebiliriz.
LayoutEnumerator layoutEnumerator = new LayoutEnumerator(doc);

Assert.AreEqual(LayoutEntityType.Page, layoutEnumerator.Type);

// LayoutEnumerator, bir ağaç gibi düzen varlıklarının koleksiyonunu geçebilir.
// Herhangi bir düğümün karşılık gelen düzen varlığına da uygulayabiliriz.
layoutEnumerator.Current = layoutCollector.GetEntity(doc.GetChild(NodeType.Paragraph, 1, true));

Assert.AreEqual(LayoutEntityType.Span, layoutEnumerator.Type);
Assert.AreEqual("¶", layoutEnumerator.Text);
```

### Ayrıca bakınız

* class [Document](../../../aspose.words/document/)
* class [LayoutCollector](../)
* ad alanı [Aspose.Words.Layout](../../layoutcollector/)
* toplantı [Aspose.Words](../../../)


