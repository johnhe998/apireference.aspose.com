---
title: Class LayoutCollector
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Layout.LayoutCollector فصل. تسمح هذه الفئة بحساب أرقام الصفحات لعقد المستند.
type: docs
weight: 3120
url: /ar/net/aspose.words.layout/layoutcollector/
---
## LayoutCollector class

تسمح هذه الفئة بحساب أرقام الصفحات لعقد المستند.

```csharp
public class LayoutCollector
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [LayoutCollector](layoutcollector/)(Document) | تهيئة مثيل لهذه الفئة . |

## الخصائص

| اسم | وصف |
| --- | --- |
| [Document](../../aspose.words.layout/layoutcollector/document/) { get; set; } | الحصول على المستند المرفق به نسخة المُجمع هذه أو تعيينها. |

## طُرق

| اسم | وصف |
| --- | --- |
| [Clear](../../aspose.words.layout/layoutcollector/clear/)() | مسح كافة بيانات التخطيط المجمعة. قم باستدعاء هذه الطريقة بعد تحديث المستند يدويًا أو إعادة تصميم التخطيط. |
| [GetEndPageIndex](../../aspose.words.layout/layoutcollector/getendpageindex/)(Node) | الحصول على فهرس يستند إلى 1 للصفحة التي تنتهي فيها العقدة. تُرجع القيمة 0 إذا تعذر تعيين العقدة إلى الصفحة. |
| [GetEntity](../../aspose.words.layout/layoutcollector/getentity/)(Node) | إرجاع موضع معتم لملف[`LayoutEnumerator`](../layoutenumerator/) التي تتوافق مع العقدة المحددة. يمكنك استخدام القيمة التي تم إرجاعها كوسيطة ل[`Current`](../layoutenumerator/current/) بالنظر إلى أن المستند يتم تعداده وأن مستند العقدة هو نفسه. |
| [GetNumPagesSpanned](../../aspose.words.layout/layoutcollector/getnumpagesspanned/)(Node) | الحصول على عدد الصفحات التي تمتد العقدة المحددة إليها. 0 إذا كانت العقدة داخل صفحة واحدة . هذا هو نفسه[`GetEndPageIndex`](./getendpageindex/) -[`GetStartPageIndex`](./getstartpageindex/) . |
| [GetStartPageIndex](../../aspose.words.layout/layoutcollector/getstartpageindex/)(Node) | الحصول على فهرس يستند إلى 1 للصفحة حيث تبدأ العقدة. تُرجع القيمة 0 إذا تعذر تعيين العقدة إلى الصفحة. |

### ملاحظات

عندما تقوم بإنشاء ملف`LayoutCollector` وتحديد أ[`Document`](../../aspose.words/document/)كائن المستند المراد إرفاقه ، سيقوم المُجمع بتسجيل تعيين عقد المستند لتخطيط الكائنات عند تنسيق المستند في صفحات.

سوف تكون قادرًا على معرفة الصفحة التي توجد بها عقدة مستند معينة (على سبيل المثال ، تشغيل أو فقرة أو خلية جدول) باستخدام[`GetStartPageIndex`](./getstartpageindex/) و[`GetEndPageIndex`](./getendpageindex/) و[`GetNumPagesSpanned`](./getnumpagesspanned/) طُرق. تقوم هذه الطرق تلقائيًا ببناء نموذج تخطيط الصفحة للمستند وتحديث الحقول إذا لزم الأمر.

عندما لم تعد بحاجة إلى جمع معلومات التخطيط ، فمن الأفضل تعيين ملف[`Document`](./document/) إلى null لتجنب التجميع غير الضروري لمزيد من تعيينات التخطيط.

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

* مساحة الاسم [Aspose.Words.Layout](../../aspose.words.layout/)
* المجسم [Aspose.Words](../../)


