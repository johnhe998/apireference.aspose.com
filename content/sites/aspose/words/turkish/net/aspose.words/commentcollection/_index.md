---
title: Class CommentCollection
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.CommentCollection sınıf. Bir koleksiyona yazılı erişim sağlarComment düğümler.
type: docs
weight: 230
url: /tr/net/aspose.words/commentcollection/
---
## CommentCollection class

Bir koleksiyona yazılı erişim sağlar[`Comment`](../comment/) düğümler.

```csharp
public class CommentCollection : NodeCollection
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Koleksiyondaki düğüm sayısını alır. |
| [Item](../../aspose.words/commentcollection/item/) { get; } | Bir **Yorum** verilen dizinde. (2 indexers) |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | Koleksiyonun sonuna bir düğüm ekler. |
| [Clear](../../aspose.words/nodecollection/clear/)() | Bu koleksiyondaki ve belgedeki tüm düğümleri kaldırır. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | Koleksiyonda bir düğüm olup olmadığını belirler. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | Düğüm koleksiyonu üzerinde basit bir "foreach" stili yineleme sağlar. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | Belirtilen düğümün sıfır tabanlı dizinini döndürür. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | Belirtilen dizindeki koleksiyona bir düğüm ekler. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | Düğümü koleksiyondan ve belgeden kaldırır. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | Belirtilen dizindeki düğümü koleksiyondan ve belgeden kaldırır. |
| [ToArray](../../aspose.words/nodecollection/toarray/)() | Koleksiyondaki tüm düğümleri yeni bir düğüm dizisine kopyalar. |

### Örnekler

Bir yorumun nasıl "tamamlandı" olarak işaretleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Helo world!");

// Bir hatayı belirtmek için bir yorum ekleyin. 
Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("Fix the spelling error!");
doc.FirstSection.Body.FirstParagraph.AppendChild(comment);

// Yorumlar, varsayılan olarak "yanlış" olarak ayarlanmış bir "Bitti" bayrağına sahiptir. 
// Bir yorum, belgede değişiklik yapmamızı önerirse,
// değişikliği uygulayabilir ve ardından düzeltmeyi belirtmek için daha sonra "Bitti" bayrağını ayarlayabiliriz.
Assert.False(comment.Done);

doc.FirstSection.Body.FirstParagraph.Runs[0].Text = "Hello world!";
comment.Done = true;

// "Bitti" olan yorumlar kendilerini farklılaştıracak
// soluk metin rengiyle "bitmemiş" olanlardan.
comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("Add text to this paragraph.");
builder.CurrentParagraph.AppendChild(comment);

doc.Save(ArtifactsDir + "Comment.Done.docx");
```

### Ayrıca bakınız

* class [NodeCollection](../nodecollection/)
* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


