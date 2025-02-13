---
title: RowCollection.Item
second_title: Aspose.Words لمراجع .NET API
description: RowCollection ملكية. يسترجع أ صف في الفهرس المحدد.
type: docs
weight: 10
url: /ar/net/aspose.words.tables/rowcollection/item/
---
## RowCollection indexer

يسترجع أ **صف** في الفهرس المحدد.

```csharp
public Row this[int index] { get; }
```

| معامل | وصف |
| --- | --- |
| index | فهرس في المجموعة. |

### ملاحظات

المؤشر على أساس الصفر.

يُسمح بالفهارس السلبية وتشير إلى الوصول من الجزء الخلفي من المجموعة. على سبيل المثال -1 تعني العنصر الأخير ، -2 تعني العنصر الثاني قبل الأخير وهكذا.

إذا كان الفهرس أكبر من أو يساوي عدد العناصر في القائمة ، فسيُرجع هذا مرجعًا فارغًا.

إذا كان الفهرس سالبًا وكانت قيمته المطلقة أكبر من عدد العناصر في القائمة ، فسيُرجع هذا مرجعًا فارغًا.

### أمثلة

يوضح كيفية التكرار عبر جميع الجداول في المستند وطباعة محتويات كل خلية.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(2, tables.ToArray().Length);

for (int i = 0; i < tables.Count; i++)
{
    Console.WriteLine($"Start of Table {i}");

    RowCollection rows = tables[i].Rows;

    // يمكننا استخدام طريقة "ToArray" في مجموعة صف لاستنساخها في مصفوفة.
    Assert.AreEqual(rows, rows.ToArray());
    Assert.AreNotSame(rows, rows.ToArray());

    for (int j = 0; j < rows.Count; j++)
    {
        Console.WriteLine($"\tStart of Row {j}");

        CellCollection cells = rows[j].Cells;

        // يمكننا استخدام طريقة "ToArray" على مجموعة خلايا لاستنساخها في مصفوفة.
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

### أنظر أيضا

* class [Row](../../row/)
* class [RowCollection](../)
* مساحة الاسم [Aspose.Words.Tables](../../rowcollection/)
* المجسم [Aspose.Words](../../../)


