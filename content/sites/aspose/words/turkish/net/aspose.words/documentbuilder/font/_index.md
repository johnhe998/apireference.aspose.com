---
title: DocumentBuilder.Font
second_title: Aspose.Words for .NET API Referansı
description: DocumentBuilder mülk. Geçerli yazı tipi biçimlendirme özelliklerini temsil eden bir nesne döndürür.
type: docs
weight: 90
url: /tr/net/aspose.words/documentbuilder/font/
---
## DocumentBuilder.Font property

Geçerli yazı tipi biçimlendirme özelliklerini temsil eden bir nesne döndürür.

```csharp
public Font Font { get; }
```

### Notlar

Kullanmak **Yazı tipi** yazı tipi biçimlendirme özelliklerine erişmek ve bunları değiştirmek için.

Metin eklemeden önce yazı tipi biçimlendirmesini belirtin.

### Örnekler

Kenarlıkla çevrili bir dizenin belgeye nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

DocumentBuilder kullanılarak biçimlendirilmiş bir tablonun nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.LeftIndent = 20;

// Metin ve tablo görünümü için bazı biçimlendirme seçeneklerini ayarlayın.
builder.RowFormat.Height = 40;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;

// Bir belge oluşturucuda biçimlendirme seçeneklerini yapılandırmak bunları uygular
// imlecinin bulunduğu geçerli hücreye/satıra,
// ve bu oluşturucu kullanılarak oluşturulan tüm yeni hücreler ve satırlar.
builder.Write("Header Row,\n Cell 1");
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.Write("Header Row,\n Cell 3");
builder.EndRow();

// Oluşturmak üzere olduğumuz yeni satırlar ve hücreler için oluşturucunun biçimlendirme nesnelerini yeniden yapılandırın.
// Oluşturucu, bunları bir başlık satırı olarak öne çıkması için önceden oluşturulmuş ilk satıra uygulamayacaktır.
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30;
builder.RowFormat.HeightRule = HeightRule.Auto;
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;

builder.Write("Row 1, Cell 1.");
builder.InsertCell();
builder.Write("Row 1, Cell 2.");
builder.InsertCell();
builder.Write("Row 1, Cell 3.");
builder.EndRow();
builder.InsertCell();
builder.Write("Row 2, Cell 1.");
builder.InsertCell();
builder.Write("Row 2, Cell 2.");
builder.InsertCell();
builder.Write("Row 2, Cell 3.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "DocumentBuilder.CreateFormattedTable.docx");
```

### Ayrıca bakınız

* class [Font](../../font/)
* class [DocumentBuilder](../)
* ad alanı [Aspose.Words](../../documentbuilder/)
* toplantı [Aspose.Words](../../../)


