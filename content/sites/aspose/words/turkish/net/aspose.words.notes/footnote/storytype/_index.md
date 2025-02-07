---
title: Footnote.StoryType
second_title: Aspose.Words for .NET API Referansı
description: Footnote mülk. İade StoryType.Dipnotlar veya Öykü Türü.Son Notlar .
type: docs
weight: 60
url: /tr/net/aspose.words.notes/footnote/storytype/
---
## Footnote.StoryType property

İade **StoryType.Dipnotlar** veya **Öykü Türü.Son Notlar** .

```csharp
public override StoryType StoryType { get; }
```

### Örnekler

InlineStory düğümlerinin nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, null);

// Tablo düğümlerinde, tabloda en az bir hücre olmasını sağlayan bir "EnsureMinimum()" yöntemi bulunur.
Table table = new Table(doc);
table.EnsureMinimum();

// Bir dipnotun içine, referans sayfasının altbilgisinde görünmesini sağlayacak bir tablo yerleştirebiliriz.
Assert.That(footnote.Tables, Is.Empty);
footnote.AppendChild(table);
Assert.AreEqual(1, footnote.Tables.Count);
Assert.AreEqual(NodeType.Table, footnote.LastChild.NodeType);

// Bir InlineStory'nin bir "EnsureMinimum()" yöntemi de vardır, ancak bu durumda,
// düğümün son alt öğesinin bir paragraf olmasını sağlar,
// Microsoft Word'de kolayca tıklayıp yazı yazabilmemiz için.
footnote.EnsureMinimum();
Assert.AreEqual(NodeType.Paragraph, footnote.LastChild.NodeType);

// Küçük üst simge numarası olan bağlantının görünümünü düzenleyin
// dipnota işaret eden ana metinde.
footnote.Font.Name = "Arial";
footnote.Font.Color = Color.Green;

// Tüm satır içi hikaye düğümlerinin ilgili hikaye türleri vardır.
Assert.AreEqual(StoryType.Footnotes, footnote.StoryType);

// Yorum, başka bir satır içi hikaye türüdür.
Comment comment = (Comment)builder.CurrentParagraph.AppendChild(new Comment(doc, "John Doe", "J. D.", DateTime.Now));

// Satır içi hikaye düğümünün üst paragrafı, ana belge gövdesinden olan paragraf olacaktır.
Assert.AreEqual(doc.FirstSection.Body.FirstParagraph, comment.ParentParagraph);

// Ancak, son paragraf yorum metni içeriğindeki paragraftır,
// bir konuşma balonunda ana belge gövdesinin dışında olacak.
// Bir yorumun varsayılan olarak herhangi bir alt düğümü olmayacak,
// böylece burada da bir paragraf yerleştirmek için SureMinimum() yöntemini uygulayabiliriz.
Assert.Null(comment.LastParagraph);
comment.EnsureMinimum();
Assert.AreEqual(NodeType.Paragraph, comment.LastChild.NodeType);

// Bir paragrafımız olduğunda, bunu yapmak için oluşturucuyu hareket ettirebilir ve yorumumuzu yazabiliriz.
builder.MoveTo(comment.LastParagraph);
builder.Write("My comment.");

Assert.AreEqual(StoryType.Comments, comment.StoryType);

doc.Save(ArtifactsDir + "InlineStory.InsertInlineStoryNodes.docx");
```

### Ayrıca bakınız

* enum [StoryType](../../../aspose.words/storytype/)
* class [Footnote](../)
* ad alanı [Aspose.Words.Notes](../../footnote/)
* toplantı [Aspose.Words](../../../)


