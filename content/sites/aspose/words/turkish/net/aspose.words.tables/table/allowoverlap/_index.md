---
title: Table.AllowOverlap
second_title: Aspose.Words for .NET API Referansı
description: Table mülk. Bir kayan tablonun görüntülendiğinde belgesindeki diğer kayan nesnelerin uzantılarıyla çakışmasına izin verip vermeyeceğini alır. Varsayılan değerdoğru .
type: docs
weight: 70
url: /tr/net/aspose.words.tables/table/allowoverlap/
---
## Table.AllowOverlap property

Bir kayan tablonun, görüntülendiğinde belgesindeki diğer kayan nesnelerin uzantılarıyla çakışmasına izin verip vermeyeceğini alır. Varsayılan değer`doğru` .

```csharp
public bool AllowOverlap { get; }
```

### Örnekler

Kayan tablo özellikleriyle nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

if (table.TextWrapping == TextWrapping.Around)
{
    Assert.AreEqual(RelativeHorizontalPosition.Margin, table.HorizontalAnchor);
    Assert.AreEqual(RelativeVerticalPosition.Paragraph, table.VerticalAnchor);
    Assert.AreEqual(false, table.AllowOverlap);

    // HorizontalAnchor ayarlayıcı için RelativeHorizontalPosition'da yalnızca Margin, Page, Column kullanılabilir.
    // Diğer değerler için ArgumentException oluşturulacak.
    table.HorizontalAnchor = RelativeHorizontalPosition.Column;

    // VerticalAnchor ayarlayıcı için RelativeVerticalPosition'da yalnızca Kenar Boşluğu, Sayfa, Paragraf kullanılabilir.
    // Diğer değerler için ArgumentException oluşturulacak.
    table.VerticalAnchor = RelativeVerticalPosition.Page;
}
```

### Ayrıca bakınız

* class [Table](../)
* ad alanı [Aspose.Words.Tables](../../table/)
* toplantı [Aspose.Words](../../../)


