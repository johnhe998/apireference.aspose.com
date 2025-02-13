---
title: CellCollection.ToArray
second_title: Aspose.Words for .NET API Referansı
description: CellCollection yöntem. Koleksiyondaki tüm hücreleri yeni bir hücre dizisine kopyalar.
type: docs
weight: 20
url: /tr/net/aspose.words.tables/cellcollection/toarray/
---
## CellCollection.ToArray method

Koleksiyondaki tüm hücreleri yeni bir hücre dizisine kopyalar.

```csharp
public Cell[] ToArray()
```

### Geri dönüş değeri

Bir dizi hücre.

### Örnekler

Belgedeki tüm tabloların nasıl yineleneceğini ve her hücrenin içeriğinin nasıl yazdırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(2, tables.ToArray().Length);

for (int i = 0; i < tables.Count; i++)
{
    Console.WriteLine($"Start of Table {i}");

    RowCollection rows = tables[i].Rows;

    // Bir diziye klonlamak için bir satır koleksiyonunda "ToArray" yöntemini kullanabiliriz.
    Assert.AreEqual(rows, rows.ToArray());
    Assert.AreNotSame(rows, rows.ToArray());

    for (int j = 0; j < rows.Count; j++)
    {
        Console.WriteLine($"\tStart of Row {j}");

        CellCollection cells = rows[j].Cells;

        // Bir hücre koleksiyonunu bir diziye klonlamak için "ToArray" yöntemini kullanabiliriz.
        Assert.AreEqual(cells, cells.ToArray());
        Assert.AreNotSame(cells, cells.ToArray());

        for (int k = 0; k < cells.Count; k++)
        {
            string cellText = cells[k].ToString(SaveFormat.Text).Trim();
            Console.WriteLine($"\t\tContents of Cell:{k} = \"{cellText}\"");
        }

        Console.WriteLine($"\tEnd of Row {j}");
    }

    Console.WriteLine($"End of Table {i}\n");
}
```

### Ayrıca bakınız

* class [Cell](../../cell/)
* class [CellCollection](../)
* ad alanı [Aspose.Words.Tables](../../cellcollection/)
* toplantı [Aspose.Words](../../../)


