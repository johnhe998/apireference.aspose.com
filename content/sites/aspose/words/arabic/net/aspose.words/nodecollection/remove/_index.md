---
title: NodeCollection.Remove
second_title: Aspose.Words لمراجع .NET API
description: NodeCollection طريقة. يزيل العقدة من المجموعة ومن الوثيقة.
type: docs
weight: 90
url: /ar/net/aspose.words/nodecollection/remove/
---
## NodeCollection.Remove method

يزيل العقدة من المجموعة ومن الوثيقة.

```csharp
public void Remove(Node node)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| node | Node | العقدة المراد إزالتها. |

### أمثلة

يوضح كيفية العمل مع NodeCollection.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أضف نصًا إلى المستند بإدراج Runs باستخدام DocumentBuilder.
builder.Write("Run 1. ");
builder.Write("Run 2. ");

// يؤدي كل استدعاء لطريقة "الكتابة" إلى إنشاء تشغيل جديد ،
// الذي يظهر بعد ذلك في RunCollection للفقرة الأصل.
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;

Assert.AreEqual(2, runs.Count);

// يمكننا أيضًا إدخال عقدة في RunCollection يدويًا.
Run newRun = new Run(doc, "Run 3. ");
runs.Insert(3, newRun);

Assert.True(runs.Contains(newRun));
Assert.AreEqual("Run 1. Run 2. Run 3.", doc.GetText().Trim());

// الوصول إلى عمليات التشغيل الفردية وإزالتها لإزالة نصها من المستند.
Run run = runs[1];
runs.Remove(run);

Assert.AreEqual("Run 1. Run 3.", doc.GetText().Trim());
Assert.NotNull(run);
Assert.False(runs.Contains(run));
```

### أنظر أيضا

* class [Node](../../node/)
* class [NodeCollection](../)
* مساحة الاسم [Aspose.Words](../../nodecollection/)
* المجسم [Aspose.Words](../../../)


