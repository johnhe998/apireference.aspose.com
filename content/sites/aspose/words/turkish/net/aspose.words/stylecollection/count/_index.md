---
title: StyleCollection.Count
second_title: Aspose.Words for .NET API Referansı
description: StyleCollection mülk. Koleksiyondaki stil sayısını alır.
type: docs
weight: 10
url: /tr/net/aspose.words/stylecollection/count/
---
## StyleCollection.Count property

Koleksiyondaki stil sayısını alır.

```csharp
public int Count { get; }
```

### Örnekler

Bir belgenin stil koleksiyonuna nasıl Stil ekleneceğini gösterir.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// Daha sonra bu koleksiyona ekleyebileceğimiz yeni stiller için varsayılan parametreleri ayarlayın.
styles.DefaultFont.Name = "Courier New";

// "StyleType.Paragraph"ın bir stilini eklersek, koleksiyon şu değerleri uygulayacaktır:
// "DefaultParagraphFormat" özelliğinden stilin "ParagraphFormat" özelliğine.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// Bir stil ekleyin ve ardından varsayılan ayarlara sahip olduğunu doğrulayın.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### Ayrıca bakınız

* class [StyleCollection](../)
* ad alanı [Aspose.Words](../../stylecollection/)
* toplantı [Aspose.Words](../../../)


