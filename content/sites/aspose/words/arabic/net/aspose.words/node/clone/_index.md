---
title: Node.Clone
second_title: Aspose.Words لمراجع .NET API
description: Node طريقة. لإنشاء نسخة مكررة من العقدة .
type: docs
weight: 100
url: /ar/net/aspose.words/node/clone/
---
## Node.Clone method

لإنشاء نسخة مكررة من العقدة .

```csharp
public Node Clone(bool isCloneChildren)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| isCloneChildren | Boolean | صحيح لاستنساخ الشجرة الفرعية بشكل متكرر تحت العقدة المحددة ؛ خطأ لاستنساخ العقدة نفسها فقط. |

### قيمة الإرجاع

العقدة المستنسخة.

### ملاحظات

تعمل هذه الطريقة كمُنشئ نسخ للعقد. العقدة المستنسخة ليس لها أصل ، ولكنها تنتمي إلى نفس المستند مثل العقدة الأصلية.

تقوم هذه الطريقة دائمًا بإجراء نسخة عميقة من العقدة. الisCloneChildren تحدد المعلمة parameter ما إذا كان سيتم إجراء نسخ جميع العقد الفرعية أيضًا.

### أمثلة

يوضح كيفية استنساخ عقدة مركبة.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;
para.AppendChild(new Run(doc, "Hello world!"));

// فيما يلي طريقتان لاستنساخ عقدة مركبة.
// 1 - أنشئ نسخة من عقدة ، وأنشئ نسخة من كل عقد من العقد الفرعية أيضًا.
Node cloneWithChildren = para.Clone(true);

Assert.IsTrue(((CompositeNode)cloneWithChildren).HasChildNodes);
Assert.AreEqual("Hello world!", cloneWithChildren.GetText().Trim());

// 2 - قم بإنشاء نسخة من العقدة من تلقاء نفسها دون أي توابع.
Node cloneWithoutChildren = para.Clone(false);

Assert.IsFalse(((CompositeNode)cloneWithoutChildren).HasChildNodes);
Assert.AreEqual(string.Empty, cloneWithoutChildren.GetText().Trim());
```

### أنظر أيضا

* class [Node](../)
* مساحة الاسم [Aspose.Words](../../node/)
* المجسم [Aspose.Words](../../../)


