---
title: Class TableCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Tables.TableCollection فصل. يوفر وصولاً مكتوبًا إلى مجموعة منTable العقد .
type: docs
weight: 6060
url: /ar/net/aspose.words.tables/tablecollection/
---
## TableCollection class

يوفر وصولاً مكتوبًا إلى مجموعة من[`Table`](../table/) العقد .

```csharp
public class TableCollection : NodeCollection
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | الحصول على عدد العقد في المجموعة. |
| [Item](../../aspose.words.tables/tablecollection/item/) { get; } | يسترجع أ **الطاولة** في الفهرس المحدد. (2 indexers) |

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
| [ToArray](../../aspose.words.tables/tablecollection/toarray/#toarray_1)() | نسخ كل الجداول من المجموعة إلى مصفوفة جداول جديدة. (2 methods) |

### أمثلة

يوضح كيفية إزالة الصفين الأول والأخير من كل الجداول في المستند.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(5, tables[0].Rows.Count);
Assert.AreEqual(4, tables[1].Rows.Count);

foreach (Table table in tables.OfType<Table>())
{
    table.FirstRow?.Remove();
    table.LastRow?.Remove();
}

Assert.AreEqual(3, tables[0].Rows.Count);
Assert.AreEqual(2, tables[1].Rows.Count);
```

يوضح كيفية معرفة ما إذا كانت الجداول متداخلة.

```csharp
public void CalculateDepthOfNestedTables()
{
    Document doc = new Document(MyDir + "Nested tables.docx");
    NodeCollection tables = doc.GetChildNodes(NodeType.Table, true);

    for (int i = 0; i < tables.Count; i++)
    {
        Table table = (Table)tables[i];

        // اكتشف ما إذا كانت أي خلايا في الجدول تحتوي على جداول أخرى كأطفال.
        int count = GetChildTableCount(table);
        Console.WriteLine("Table #{0} has {1} tables directly within its cells", i, count);

        // اكتشف ما إذا كان الجدول متداخلًا داخل جدول آخر ، وإذا كان الأمر كذلك ، فبأي عمق.
        int tableDepth = GetNestedDepthOfTable(table);

        if (tableDepth > 0)
            Console.WriteLine("Table #{0} is nested inside another table at depth of {1}", i,
                tableDepth);
        else
            Console.WriteLine("Table #{0} is a non nested table (is not a child of another table)", i);
    }
}

/// <summary>
/// لحساب المستوى الذي يتداخل فيه الجدول داخل جداول أخرى.
/// </summary>
/// <returns>
/// عدد صحيح يشير إلى عمق تداخل الجدول (عدد عقد الجدول الأصل).
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
/// يحدد ما إذا كان الجدول يحتوي على أي جدول تابع مباشر داخل خلاياه.
/// لا تجتاز هذه الجداول بشكل متكرر للتحقق من وجود المزيد من الجداول.
/// </summary>
/// <returns>
/// يعود صحيحاً إذا احتوت خلية فرعية واحدة على الأقل على جدول.
/// ترجع خطأ إذا لم تكن هناك خلايا في الجدول تحتوي على جدول.
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

### أنظر أيضا

* class [NodeCollection](../../aspose.words/nodecollection/)
* مساحة الاسم [Aspose.Words.Tables](../../aspose.words.tables/)
* المجسم [Aspose.Words](../../)


