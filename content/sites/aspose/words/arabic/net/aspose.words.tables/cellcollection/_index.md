---
title: Class CellCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Tables.CellCollection فصل. يوفر وصولاً مكتوبًا إلى مجموعة منCell العقد .
type: docs
weight: 5950
url: /ar/net/aspose.words.tables/cellcollection/
---
## CellCollection class

يوفر وصولاً مكتوبًا إلى مجموعة من[`Cell`](../cell/) العقد .

```csharp
public class CellCollection : NodeCollection
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | الحصول على عدد العقد في المجموعة. |
| [Item](../../aspose.words.tables/cellcollection/item/) { get; } | يسترجع أ **خلية** في الفهرس المحدد. (2 indexers) |

## طُرق

| اسم | وصف |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | يضيف عقدة إلى نهاية المجموعة. |
| [Clear](../../aspose.words/nodecollection/clear/)() | يزيل كافة العقد من هذه المجموعة ومن المستند. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | لتحديد ما إذا كانت العقدة موجودة في المجموعة. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | يوفر تكرارًا بسيطًا لنمط "foreach" عبر مجموعة العقد. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | إرجاع الفهرس الصفري للعقدة المحددة. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | إدراج عقدة في المجموعة بالفهرس المحدد. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | يزيل العقدة من المجموعة ومن الوثيقة. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | يزيل العقدة في الفهرس المحدد من المجموعة ومن المستند. |
| [ToArray](../../aspose.words.tables/cellcollection/toarray/#toarray_1)() | نسخ جميع الخلايا من المجموعة إلى صفيف جديد من الخلايا. (2 methods) |

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

* class [NodeCollection](../../aspose.words/nodecollection/)
* مساحة الاسم [Aspose.Words.Tables](../../aspose.words.tables/)
* المجسم [Aspose.Words](../../)


