---
title: LayoutCollector.GetEntity
second_title: Aspose.Words لمراجع .NET API
description: LayoutCollector طريقة. إرجاع موضع معتم لملفLayoutEnumerator التي تتوافق مع العقدة المحددة. يمكنك استخدام القيمة التي تم إرجاعها كوسيطة لCurrent بالنظر إلى أن المستند يتم تعداده وأن مستند العقدة هو نفسه.
type: docs
weight: 50
url: /ar/net/aspose.words.layout/layoutcollector/getentity/
---
## LayoutCollector.GetEntity method

إرجاع موضع معتم لملف[`LayoutEnumerator`](../../layoutenumerator/) التي تتوافق مع العقدة المحددة. يمكنك استخدام القيمة التي تم إرجاعها كوسيطة ل[`Current`](../../layoutenumerator/current/) بالنظر إلى أن المستند يتم تعداده وأن مستند العقدة هو نفسه.

```csharp
public object GetEntity(Node node)
```

### ملاحظات

هذه الطريقة تعمل فقط[`Paragraph`](../../../aspose.words/paragraph/) العقد ، وكذلك العقد المضمنة غير القابلة للتجزئة ، على سبيل المثال[`BookmarkStart`](../../../aspose.words/bookmarkstart/) أو[`Shape`](../../../aspose.words.drawing/shape/) إنه لا يعمل من أجل[`Run`](../../../aspose.words/run/) و[`Cell`](../../../aspose.words.tables/cell/)[`Row`](../../../aspose.words.tables/row/) أو[`Table`](../../../aspose.words.tables/table/) العقد والعقد داخل الرأس / التذييل.

لاحظ أن الكيان تم إرجاعه لـ[`Paragraph`](../../../aspose.words/paragraph/) العقدة هي فترة فاصلة للفقرة. استخدم الطريقة المناسبة للصعود إلى السطر الأصل

إذا كنت بحاجة إلى الانتقال إلى ملف[`Run`](../../../aspose.words/run/) من النص ، يمكنك إدخال إشارة مرجعية مباشرة قبل it ثم الانتقال إلى الإشارة المرجعية بدلاً من ذلك.

إذا كنت بحاجة إلى الانتقال إلى ملف[`Cell`](../../../aspose.words.tables/cell/) عقدة ثم يمكنك الانتقال إلى[`Paragraph`](../../../aspose.words/paragraph/) في هذه الخلية ثم تصعد إلى الكيان الأصل. يمكن استخدام نفس النهج ل[`Row`](../../../aspose.words.tables/row/) و[`Table`](../../../aspose.words.tables/table/) العقد.

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


