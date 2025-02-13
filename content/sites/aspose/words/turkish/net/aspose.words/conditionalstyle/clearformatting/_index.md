---
title: ConditionalStyle.ClearFormatting
second_title: Aspose.Words for .NET API Referansı
description: ConditionalStyle yöntem. Bu koşullu stilin biçimlendirmesini temizler.
type: docs
weight: 100
url: /tr/net/aspose.words/conditionalstyle/clearformatting/
---
## ConditionalStyle.ClearFormatting method

Bu koşullu stilin biçimlendirmesini temizler.

```csharp
public void ClearFormatting()
```

### Örnekler

Koşullu tablo stillerinin nasıl sıfırlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("First row");
builder.EndRow();
builder.InsertCell();
builder.Write("Last row");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
table.Style = tableStyle;

// Tablonun ilk satırının kenarlıklarını kırmızıya boyamak için tablo stilini ayarlayın.
tableStyle.ConditionalStyles.FirstRow.Borders.Color = Color.Red;

// Tablonun son satırının kenarlıklarını mavi renklendirmek için tablo stilini ayarlayın.
tableStyle.ConditionalStyles.LastRow.Borders.Color = Color.Blue;

// Koşullu stilleri temizlemek için "ClearFormatting" yöntemini kullanmanın iki yolu aşağıdadır.
// 1 - Tablonun belirli bir bölümü için koşullu stilleri temizleyin:
tableStyle.ConditionalStyles[0].ClearFormatting();

Assert.AreEqual(Color.Empty, tableStyle.ConditionalStyles.FirstRow.Borders.Color);

// 2 - Tüm tablo için koşullu stilleri temizleyin:
tableStyle.ConditionalStyles.ClearFormatting();

Assert.True(tableStyle.ConditionalStyles.All(s => s.Borders.Color == Color.Empty));
```

### Ayrıca bakınız

* class [ConditionalStyle](../)
* ad alanı [Aspose.Words](../../conditionalstyle/)
* toplantı [Aspose.Words](../../../)


