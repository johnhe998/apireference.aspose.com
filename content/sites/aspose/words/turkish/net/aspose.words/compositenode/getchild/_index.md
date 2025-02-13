---
title: CompositeNode.GetChild
second_title: Aspose.Words for .NET API Referansı
description: CompositeNode yöntem. Belirtilen türle eşleşen N. alt düğümü döndürür.
type: docs
weight: 90
url: /tr/net/aspose.words/compositenode/getchild/
---
## CompositeNode.GetChild method

Belirtilen türle eşleşen N. alt düğümü döndürür.

```csharp
public Node GetChild(NodeType nodeType, int index, bool isDeep)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| nodeType | NodeType | Alt düğümün türünü belirtir. |
| index | Int32 | Seçilecek alt düğümün sıfır tabanlı dizini. Negatif dizinlere de izin verilir ve sondan erişimi gösterir, yani -1, son düğüm anlamına gelir. |
| isDeep | Boolean | Tüm alt düğümlerden özyinelemeli olarak seçim yapmak için true. Yalnızca en yakın alt öğeler arasından seçim yapmak için False. Daha fazla bilgi için açıklamalara bakın. |

### Geri dönüş değeri

Ölçütle eşleşen alt düğüm veya eşleşen bir düğüm bulunamazsa boş.

### Notlar

Dizin aralık dışındaysa, bir boş değer döndürülür.

İşaretleme düğümlerinin (StructuredDocumentTag veSmartTag) , isDeep = false olduğunda ve biçimlendirme olmayan düğüm türü için GetChild çağrıldığında bile geçilir. Örneğin, bir para içindeki ilk çalıştırma bir StructuredDocumentTag içine sarılmışsa, yine de GetChild(NodeType.Run, 0, false) tarafından döndürülecektir.

### Örnekler

Bir tablonun stilinin özelliklerinin doğrudan tablonun öğelerine nasıl uygulanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Hello world!");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.RowStripe = 3;
tableStyle.CellSpacing = 5;
tableStyle.Shading.BackgroundPatternColor = Color.AntiqueWhite;
tableStyle.Borders.Color = Color.Blue;
tableStyle.Borders.LineStyle = LineStyle.DotDash;

table.Style = tableStyle;

// Bu yöntem, yukarıda belirlediklerimiz gibi tablo stili özellikleriyle ilgilidir.
doc.ExpandTableStylesToDirectFormatting();

doc.Save(ArtifactsDir + "Document.TableStyleToDirectFormatting.docx");
```

Bileşik bir düğümün alt düğüm koleksiyonunda nasıl geçileceğini gösterir.

```csharp
Document doc = new Document();

// Bu belgenin ilk paragrafına alt düğümler olarak iki işlem ve bir şekil ekleyin.
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
paragraph.AppendChild(new Run(doc, "Hello world! "));

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
// 'CustomNodeId' bir çıktı dosyasına kaydedilmediğini ve yalnızca düğüm ömrü boyunca var olduğunu unutmayın.
shape.CustomNodeId = 100;
shape.WrapType = WrapType.Inline;
paragraph.AppendChild(shape);

paragraph.AppendChild(new Run(doc, "Hello again!"));

// Paragrafın acil alt öğeleri koleksiyonunu yineleyin,
// ve içinde bulduğumuz tüm koşuları veya şekilleri yazdırın.
NodeCollection children = paragraph.ChildNodes;

Assert.AreEqual(3, paragraph.ChildNodes.Count);

foreach (Node child in children)
    switch (child.NodeType)
    {
        case NodeType.Run:
            Console.WriteLine("Run contents:");
            Console.WriteLine($"\t\"{child.GetText().Trim()}\"");
            break;
        case NodeType.Shape:
            Shape childShape = (Shape)child;
            Console.WriteLine("Shape:");
            Console.WriteLine($"\t{childShape.ShapeType}, {childShape.Width}x{childShape.Height}");
    }
```

### Ayrıca bakınız

* class [Node](../../node/)
* enum [NodeType](../../nodetype/)
* class [CompositeNode](../)
* ad alanı [Aspose.Words](../../compositenode/)
* toplantı [Aspose.Words](../../../)


