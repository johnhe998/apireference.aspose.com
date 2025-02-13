---
title: Enum CommentDisplayMode
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Layout.CommentDisplayMode Sıralama. Belge yorumları için oluşturma modunu belirtir.
type: docs
weight: 3090
url: /tr/net/aspose.words.layout/commentdisplaymode/
---
## CommentDisplayMode enumeration

Belge yorumları için oluşturma modunu belirtir.

```csharp
public enum CommentDisplayMode
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Hide | `0` | Hiçbir belge yorumu oluşturulmaz. |
| ShowInBalloons | `1` | Belge yorumlarını kenar boşluğunda balonlar halinde işler. Bu varsayılan değerdir. |
| ShowInAnnotations | `2` | Ek açıklamalarda belge yorumlarını işler. Bu yalnızca Pdf formatı için kullanılabilir. |

### Örnekler

Bir belgeyi işlenmiş bir formatta kaydederken yorumların nasıl gösterileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");

Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("My comment.");
builder.CurrentParagraph.AppendChild(comment);

// ShowInAnnotations yalnızca Pdf1.7 ve Pdf1.5 formatlarında mevcuttur.
// Diğer formatlarda, Gizle'ye benzer şekilde çalışacaktır.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.ShowInAnnotations;

doc.Save(ArtifactsDir + "Document.ShowCommentsInAnnotations.pdf");

// Belge sayfa düzenini yeniden oluşturmanın gerekli olduğunu unutmayın (Document.UpdatePageLayout() yöntemi aracılığıyla)
// Document.LayoutOptions değerlerini değiştirdikten sonra.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.ShowInBalloons;
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Document.ShowCommentsInBalloons.pdf");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Layout](../../aspose.words.layout/)
* toplantı [Aspose.Words](../../)


