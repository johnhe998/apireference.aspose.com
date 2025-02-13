---
title: NodeCollection.IndexOf
second_title: Aspose.Words لمراجع .NET API
description: NodeCollection طريقة. إرجاع الفهرس الصفري للعقدة المحددة.
type: docs
weight: 70
url: /ar/net/aspose.words/nodecollection/indexof/
---
## NodeCollection.IndexOf method

إرجاع الفهرس الصفري للعقدة المحددة.

```csharp
public int IndexOf(Node node)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| node | Node | العقدة المراد تحديد موقعها. |

### قيمة الإرجاع

الفهرس الصفري للعقدة داخل المجموعة ، إذا وجد ؛ خلاف ذلك ، -1.

### ملاحظات

تقوم هذه الطريقة بإجراء بحث خطي ؛ لذلك ، متوسط وقت التنفيذ يتناسب مع العدد.

### أمثلة

يوضح كيفية الحصول على فهرس عقدة في مجموعة.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Table table = doc.FirstSection.Body.Tables[0];
NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);

Assert.AreEqual(0, allTables.IndexOf(table));

Row row = table.Rows[2];

Assert.AreEqual(2, table.IndexOf(row));

Cell cell = row.LastCell;

Assert.AreEqual(4, row.IndexOf(cell));
```

### أنظر أيضا

* class [Node](../../node/)
* class [NodeCollection](../)
* مساحة الاسم [Aspose.Words](../../nodecollection/)
* المجسم [Aspose.Words](../../../)


