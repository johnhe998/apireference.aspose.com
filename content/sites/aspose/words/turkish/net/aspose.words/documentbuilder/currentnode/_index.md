---
title: DocumentBuilder.CurrentNode
second_title: Aspose.Words for .NET API Referansı
description: DocumentBuilder mülk. Bu DocumentBuilderda seçili olan düğümü alır.
type: docs
weight: 40
url: /tr/net/aspose.words/documentbuilder/currentnode/
---
## DocumentBuilder.CurrentNode property

Bu DocumentBuilder'da seçili olan düğümü alır.

```csharp
public Node CurrentNode { get; }
```

### Notlar

**Geçerli Düğüm** bir imleç **Belge Oluşturucu** ve bir işaret **düğüm** bu, bir **Paragraf** . kullanarak gerçekleştirdiğiniz herhangi bir ekleme işlemi **Belge Oluşturucu** önce eklenecek **Geçerli Düğüm**.

Geçerli paragraf boş olduğunda veya imleç paragrafın sonundan önce sadece konumuna getirildiğinde, **Geçerli Düğüm** null döndürür.

### Örnekler

Bir belge oluşturucunun imlecinin bir belgedeki farklı düğümlere nasıl taşınacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Geçerli bir yer imi oluşturun, bir yer imi başlangıç düğümü tarafından çevrelenen düğümlerden oluşan bir varlık,
 // ve bir yer imi bitiş düğümü.
builder.StartBookmark("MyBookmark");
builder.Write("Bookmark contents.");
builder.EndBookmark("MyBookmark");

NodeCollection firstParagraphNodes = doc.FirstSection.Body.FirstParagraph.ChildNodes;

Assert.AreEqual(NodeType.BookmarkStart, firstParagraphNodes[0].NodeType);
Assert.AreEqual(NodeType.Run, firstParagraphNodes[1].NodeType);
Assert.AreEqual("Bookmark contents.", firstParagraphNodes[1].GetText().Trim());
Assert.AreEqual(NodeType.BookmarkEnd, firstParagraphNodes[2].NodeType);

// Belge oluşturucunun imleci her zaman onunla son eklediğimiz düğümün önündedir.
// Oluşturucunun imleci belgenin sonundaysa, mevcut düğümü boş olur.
// Önceki düğüm, en son eklediğimiz yer imi bitiş düğümüdür.
// Oluşturucu ile yeni düğümler eklemek onları son düğüme ekleyecektir.
Assert.Null(builder.CurrentNode);

// Oluşturucu ile belgenin farklı bir bölümünü düzenlemek istersek,
// imlecini düzenlemek istediğimiz düğüme getirmemiz gerekecek.
builder.MoveToBookmark("MyBookmark");

// Onu bir yer imine taşımak, onu yer imi başlangıç ve bitiş düğümleri içindeki ilk düğüme, ekteki çalıştırmaya taşır.
Assert.AreEqual(firstParagraphNodes[1], builder.CurrentNode);

// İmleci bu şekilde tek bir düğüme de taşıyabiliriz.
builder.MoveTo(doc.FirstSection.Body.FirstParagraph.GetChildNodes(NodeType.Any, false)[0]);

Assert.AreEqual(NodeType.BookmarkStart, builder.CurrentNode.NodeType);
Assert.AreEqual(doc.FirstSection.Body.FirstParagraph, builder.CurrentParagraph);
Assert.IsTrue(builder.IsAtStartOfParagraph);

// Bir belgenin başına/sonuna gitmek için belirli yöntemler kullanabiliriz.
builder.MoveToDocumentEnd();

Assert.IsTrue(builder.IsAtEndOfParagraph);

builder.MoveToDocumentStart();

Assert.IsTrue(builder.IsAtStartOfParagraph);
```

### Ayrıca bakınız

* class [Node](../../node/)
* class [DocumentBuilder](../)
* ad alanı [Aspose.Words](../../documentbuilder/)
* toplantı [Aspose.Words](../../../)


