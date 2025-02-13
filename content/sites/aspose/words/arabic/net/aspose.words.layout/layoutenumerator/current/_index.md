---
title: LayoutEnumerator.Current
second_title: Aspose.Words لمراجع .NET API
description: LayoutEnumerator ملكية. الحصول على أو تعيين الموضع الحالي في نموذج تخطيط الصفحة . هذه الخاصية تُرجع كائنًا معتمًا يتوافق مع كيان التخطيط الحالي.
type: docs
weight: 20
url: /ar/net/aspose.words.layout/layoutenumerator/current/
---
## LayoutEnumerator.Current property

الحصول على أو تعيين الموضع الحالي في نموذج تخطيط الصفحة . هذه الخاصية تُرجع كائنًا معتمًا يتوافق مع كيان التخطيط الحالي.

```csharp
public object Current { get; set; }
```

### أمثلة

يوضح كيفية مشاهدة نطاقات الصفحات التي تمتد العقدة.

```csharp
Document doc = new Document();
LayoutCollector layoutCollector = new LayoutCollector(doc);

// اتصل بطريقة "GetNumPagesSpanned" لحساب عدد الصفحات التي يمتد محتوى وثيقتنا عليها.
// نظرًا لأن المستند فارغًا ، فإن هذا العدد من الصفحات هو صفر حاليًا.
Assert.AreEqual(doc, layoutCollector.Document);
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

// ملء المستند بـ 5 صفحات من المحتوى.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Section 1");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);

// قبل جامع التخطيط ، نحتاج إلى استدعاء طريقة "UpdatePageLayout" لإعطائنا
// رقم دقيق لأي مقياس متعلق بالتنسيق ، مثل عدد الصفحات.
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

layoutCollector.Clear();
doc.UpdatePageLayout();

Assert.AreEqual(5, layoutCollector.GetNumPagesSpanned(doc));

// يمكننا أن نرى أرقام صفحات البداية والنهاية لأي عقدة وامتدادات صفحتها الإجمالية.
NodeCollection nodes = doc.GetChildNodes(NodeType.Any, true);
foreach (Node node in nodes)
{
    Console.WriteLine($"->  NodeType.{node.NodeType}: ");
    Console.WriteLine(
        $"\tStarts on page {layoutCollector.GetStartPageIndex(node)}, ends on page {layoutCollector.GetEndPageIndex(node)}," +
        $" spanning {layoutCollector.GetNumPagesSpanned(node)} pages.");
}

// يمكننا التكرار عبر كيانات التخطيط باستخدام LayoutEnumerator.
LayoutEnumerator layoutEnumerator = new LayoutEnumerator(doc);

Assert.AreEqual(LayoutEntityType.Page, layoutEnumerator.Type);

// يمكن لـ LayoutEnumerator اجتياز مجموعة كيانات التخطيط مثل الشجرة.
// يمكننا أيضًا تطبيقه على أي كيان تخطيط مطابق لأي عقدة.
layoutEnumerator.Current = layoutCollector.GetEntity(doc.GetChild(NodeType.Paragraph, 1, true));

Assert.AreEqual(LayoutEntityType.Span, layoutEnumerator.Type);
Assert.AreEqual("¶", layoutEnumerator.Text);
```

### أنظر أيضا

* class [LayoutEnumerator](../)
* مساحة الاسم [Aspose.Words.Layout](../../layoutenumerator/)
* المجسم [Aspose.Words](../../../)


