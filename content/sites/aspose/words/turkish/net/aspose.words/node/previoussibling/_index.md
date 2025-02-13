---
title: Node.PreviousSibling
second_title: Aspose.Words for .NET API Referansı
description: Node mülk. Bu düğümden hemen önceki düğümü alır.
type: docs
weight: 70
url: /tr/net/aspose.words/node/previoussibling/
---
## Node.PreviousSibling property

Bu düğümden hemen önceki düğümü alır.

```csharp
public Node PreviousSibling { get; }
```

### Notlar

Önceki düğüm yoksa, bir boş değer döndürülür.

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

* class [Node](../)
* ad alanı [Aspose.Words](../../node/)
* toplantı [Aspose.Words](../../../)


