---
title: LayoutCollector.GetEndPageIndex
second_title: Aspose.Words لمراجع .NET API
description: LayoutCollector طريقة. الحصول على فهرس يستند إلى 1 للصفحة التي تنتهي فيها العقدة. تُرجع القيمة 0 إذا تعذر تعيين العقدة إلى الصفحة.
type: docs
weight: 40
url: /ar/net/aspose.words.layout/layoutcollector/getendpageindex/
---
## LayoutCollector.GetEndPageIndex method

الحصول على فهرس يستند إلى 1 للصفحة التي تنتهي فيها العقدة. تُرجع القيمة 0 إذا تعذر تعيين العقدة إلى الصفحة.

```csharp
public int GetEndPageIndex(Node node)
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

* class [Node](../../../aspose.words/node/)
* class [LayoutCollector](../)
* مساحة الاسم [Aspose.Words.Layout](../../layoutcollector/)
* المجسم [Aspose.Words](../../../)


