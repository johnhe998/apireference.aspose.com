---
title: CompositeNode.LastChild
second_title: Aspose.Words for .NET API Referansı
description: CompositeNode mülk. Düğümün son alt öğesini alır.
type: docs
weight: 60
url: /tr/net/aspose.words/compositenode/lastchild/
---
## CompositeNode.LastChild property

Düğümün son alt öğesini alır.

```csharp
public Node LastChild { get; }
```

### Notlar

Son alt düğüm yoksa null döndürülür.

### Örnekler

Belgedeki son bölümden önceki bir bölümü kaldırmak için Node ve CompositeNode yöntemlerinin nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1 text.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2 text.");

// Her iki bölüm de birbirinin kardeşidir.
Section lastSection = (Section)doc.LastChild;
Section firstSection = (Section)lastSection.PreviousSibling;

// Başka bir bölümle kardeş ilişkisine göre bir bölümü kaldırın.
if (lastSection.PreviousSibling != null)
    doc.RemoveChild(firstSection);

// Kaldırdığımız bölüm ilk bölümdü ve belgeyi sadece ikinci bölümle bıraktı.
Assert.AreEqual("Section 2 text.", doc.GetText().Trim());
```

### Ayrıca bakınız

* class [Node](../../node/)
* class [CompositeNode](../)
* ad alanı [Aspose.Words](../../compositenode/)
* toplantı [Aspose.Words](../../../)


