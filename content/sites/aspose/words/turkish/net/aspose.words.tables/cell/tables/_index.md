---
title: Cell.Tables
second_title: Aspose.Words for .NET API Referansı
description: Cell mülk. Hücrenin hemen alt öğeleri olan tabloların bir koleksiyonunu alır.
type: docs
weight: 100
url: /tr/net/aspose.words.tables/cell/tables/
---
## Cell.Tables property

Hücrenin hemen alt öğeleri olan tabloların bir koleksiyonunu alır.

```csharp
public TableCollection Tables { get; }
```

### Örnekler

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

* class [TableCollection](../../tablecollection/)
* class [Cell](../)
* ad alanı [Aspose.Words.Tables](../../cell/)
* toplantı [Aspose.Words](../../../)


