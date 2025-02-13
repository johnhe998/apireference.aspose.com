---
title: NodeCollection.Count
second_title: Aspose.Words for .NET API Referansı
description: NodeCollection mülk. Koleksiyondaki düğüm sayısını alır.
type: docs
weight: 10
url: /tr/net/aspose.words/nodecollection/count/
---
## NodeCollection.Count property

Koleksiyondaki düğüm sayısını alır.

```csharp
public int Count { get; }
```

### Örnekler

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

Bir tablonun iç içe olup olmadığını nasıl öğreneceğinizi gösterir.

```csharp
public void CalculateDepthOfNestedTables()
{
    Document doc = new Document(MyDir + "Nested tables.docx");
    NodeCollection tables = doc.GetChildNodes(NodeType.Table, true);

    for (int i = 0; i < tables.Count; i++)
    {
        Table table = (Table)tables[i];

        // Tablodaki herhangi bir hücrenin alt öğe olarak başka tabloları olup olmadığını öğrenin.
        int count = GetChildTableCount(table);
        Console.WriteLine("Table #{0} has {1} tables directly within its cells", i, count);

        // Tablonun başka bir tablonun içinde olup olmadığını ve öyleyse hangi derinlikte olduğunu öğrenin.
        int tableDepth = GetNestedDepthOfTable(table);

        if (tableDepth > 0)
            Console.WriteLine("Table #{0} is nested inside another table at depth of {1}", i,
                tableDepth);
        else
            Console.WriteLine("Table #{0} is a non nested table (is not a child of another table)", i);
    }
}

/// <summary>
/// Bir tablonun diğer tabloların içinde hangi düzeyde iç içe olduğunu hesaplar.
/// </summary>
/// <returns>
/// Tablonun iç içe geçme derinliğini gösteren bir tam sayı (üst tablo düğümlerinin sayısı).
/// </returns>
private static int GetNestedDepthOfTable(Table table)
{
    int depth = 0;
    Node parent = table.GetAncestor(table.NodeType);

    while (parent != null)
    {
        depth++;
        parent = parent.GetAncestor(typeof(Table));
    }

    return depth;
}

/// <summary>
/// Bir tablonun hücreleri içinde herhangi bir doğrudan alt tablo içerip içermediğini belirler.
/// Daha fazla tablo olup olmadığını kontrol etmek için bu tablolar arasında tekrar tekrar dolaşmayın.
/// </summary>
/// <returns>
/// En az bir alt hücre bir tablo içeriyorsa true değerini döndürür.
/// Tablodaki hiçbir hücre tablo içermiyorsa false döndürür.
/// </returns>
private static int GetChildTableCount(Table table)
{
    int childTableCount = 0;

    foreach (Row row in table.Rows.OfType<Row>())
    {
        foreach (Cell Cell in row.Cells.OfType<Cell>())
        {
            TableCollection childTables = Cell.Tables;

            if (childTables.Count > 0)
                childTableCount++;
        }
    }

    return childTableCount;
}
```

### Ayrıca bakınız

* class [NodeCollection](../)
* ad alanı [Aspose.Words](../../nodecollection/)
* toplantı [Aspose.Words](../../../)


