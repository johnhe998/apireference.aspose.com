---
title: StyleCollection.DefaultParagraphFormat
second_title: Aspose.Words for .NET API Referansı
description: StyleCollection mülk. Belge varsayılan paragraf biçimlendirmesini alır.
type: docs
weight: 30
url: /tr/net/aspose.words/stylecollection/defaultparagraphformat/
---
## StyleCollection.DefaultParagraphFormat property

Belge varsayılan paragraf biçimlendirmesini alır.

```csharp
public ParagraphFormat DefaultParagraphFormat { get; }
```

### Notlar

Belge genelindeki varsayılanların Microsoft Word 2007'de tanıtıldığını ve OOXML biçimlerinde tam olarak desteklendiğini unutmayın (Docx) yalnızca. Daha önceki belge biçimleri, belge varsayılan paragraf biçimlendirmesini desteklemez.

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

* class [ParagraphFormat](../../paragraphformat/)
* class [StyleCollection](../)
* ad alanı [Aspose.Words](../../stylecollection/)
* toplantı [Aspose.Words](../../../)


