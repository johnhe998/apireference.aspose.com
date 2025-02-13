---
title: Story.Tables
second_title: Aspose.Words لمراجع .NET API
description: Story ملكية. الحصول على مجموعة من الجداول التي تمثل الأطفال المباشرين للقصة.
type: docs
weight: 50
url: /ar/net/aspose.words/story/tables/
---
## Story.Tables property

الحصول على مجموعة من الجداول التي تمثل الأطفال المباشرين للقصة.

```csharp
public TableCollection Tables { get; }
```

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

### أنظر أيضا

* class [TableCollection](../../../aspose.words.tables/tablecollection/)
* class [Story](../)
* مساحة الاسم [Aspose.Words](../../story/)
* المجسم [Aspose.Words](../../../)


