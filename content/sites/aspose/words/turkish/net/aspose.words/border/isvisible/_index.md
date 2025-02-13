---
title: Border.IsVisible
second_title: Aspose.Words for .NET API Referansı
description: Border mülk. LineStyle LineStyle değilse true değerini döndürür.None.
type: docs
weight: 30
url: /tr/net/aspose.words/border/isvisible/
---
## Border.IsVisible property

LineStyle, LineStyle değilse true değerini döndürür.None.

```csharp
public bool IsVisible { get; }
```

### Örnekler

Bir paragraftan kenarlıkların nasıl kaldırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Borders.docx");

// Her paragrafın ayrı bir kenarlık kümesi vardır.
// Paragraf format nesnesi üzerinden bu kenarlıkların görünümü için ayarlara ulaşabiliriz.
BorderCollection borders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;

Assert.AreEqual(Color.Red.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(3.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.Single, borders[0].LineStyle);
Assert.True(borders[0].IsVisible);

// ClearFormatting yöntemini çalıştırarak bir kerede bir kenarlığı kaldırabiliriz. 
// Bu yöntemi bir paragrafın her kenarlığında çalıştırmak tüm kenarlıklarını kaldıracaktır.
foreach (Border border in borders)
    border.ClearFormatting();

Assert.AreEqual(Color.Empty.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(0.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.None, borders[0].LineStyle);
Assert.IsFalse(borders[0].IsVisible);

doc.Save(ArtifactsDir + "Border.ClearFormatting.docx");
```

### Ayrıca bakınız

* class [Border](../)
* ad alanı [Aspose.Words](../../border/)
* toplantı [Aspose.Words](../../../)


