---
title: ListFormat.RemoveNumbers
second_title: Aspose.Words لمراجع .NET API
description: ListFormat طريقة. يزيل الأرقام أو الرموز النقطية من الفقرة الحالية ويضبط مستوى القائمة على صفر.
type: docs
weight: 90
url: /ar/net/aspose.words.lists/listformat/removenumbers/
---
## ListFormat.RemoveNumbers method

يزيل الأرقام أو الرموز النقطية من الفقرة الحالية ويضبط مستوى القائمة على صفر.

```csharp
public void RemoveNumbers()
```

### ملاحظات

استدعاء هذه الطريقة يعادل ضبط[`List`](../list/) خاصية لاغية.

### أمثلة

يوضح كيفية إزالة تنسيق القائمة من جميع الفقرات في النص الرئيسي للقسم.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Numbered list item 1");
builder.Writeln("Numbered list item 2");
builder.Writeln("Numbered list item 3");
builder.ListFormat.RemoveNumbers();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

Assert.AreEqual(3, paras.Count(n => (n as Paragraph).ListFormat.IsListItem));

foreach (Paragraph paragraph in paras)
    paragraph.ListFormat.RemoveNumbers();

Assert.AreEqual(0, paras.Count(n => (n as Paragraph).ListFormat.IsListItem));
```

يوضح كيفية إنشاء قوائم ذات تعداد نقطي ورقمي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Aspose.Words main advantages are:");

// تسمح لنا القائمة بتنظيم وتزيين مجموعات من الفقرات برموز بادئة ومسافات بادئة.
// يمكننا إنشاء قوائم متداخلة عن طريق زيادة مستوى المسافة البادئة. 
// يمكننا بدء قائمة وإنهائها باستخدام خاصية "تنسيق القائمة" الخاصة بمنشئ المستندات. 
// كل فقرة نضيفها بين بداية القائمة ونهايتها ستصبح عنصرًا في القائمة.
// يوجد أدناه نوعان من القوائم التي يمكننا إنشاؤها باستخدام أداة إنشاء المستندات.
// 1 - قائمة نقطية:
// ستطبق هذه القائمة مسافة بادئة ورمز نقطي ("•") قبل كل فقرة.
builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Great performance");
builder.Writeln("High reliability");
builder.Writeln("Quality code and working");
builder.Writeln("Wide variety of features");
builder.Writeln("Easy to understand API");

// إنهاء القائمة النقطية.
builder.ListFormat.RemoveNumbers();

builder.InsertBreak(BreakType.ParagraphBreak);
builder.Writeln("Aspose.Words allows:");

// 2 - قائمة ذات تعداد رقمي:
// تقوم القوائم المرقمة بإنشاء ترتيب منطقي لفقراتها عن طريق ترقيم كل عنصر.
builder.ListFormat.ApplyNumberDefault();

// هذه الفقرة هي العنصر الأول. سيحتوي العنصر الأول في قائمة ذات تعداد رقمي على "1". كرمز عنصر القائمة.
builder.Writeln("Opening documents from different formats:");

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// استدعاء طريقة "ListIndent" لزيادة مستوى القائمة الحالية ،
// التي ستبدأ قائمة قائمة بذاتها جديدة ، بمسافة بادئة أعمق ، في العنصر الحالي من مستوى القائمة الأول.
builder.ListFormat.ListIndent();

Assert.AreEqual(1, builder.ListFormat.ListLevelNumber);

// هذه هي عناصر القائمة الثلاثة الأولى من مستوى القائمة الثاني ، والتي ستحتفظ بالعد
// مستقل عن عدد مستوى القائمة الأول. وفقًا لتنسيق القائمة الحالي ،
// سيكون لديهم رموز "أ" و "ب" و "ج".
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");

// قم باستدعاء طريقة "ListOutdent" للعودة إلى مستوى القائمة السابق.
builder.ListFormat.ListOutdent();

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// ستستمر هاتان الفقرتان في العد لمستوى القائمة الأول.
// ستحتوي هذه العناصر على رموز "2." و "3."
builder.Writeln("Processing documents");
builder.Writeln("Saving documents in different formats:");

// إذا قمنا بزيادة مستوى القائمة إلى مستوى قمنا بإضافة عناصر إليه سابقًا ،
// ستكون القائمة المتداخلة منفصلة عن القائمة السابقة ، وسيبدأ ترقيمها من البداية. 
// ستحتوي عناصر القائمة هذه على رموز "أ" و "ب" و "ج" و "د" و "هـ".
builder.ListFormat.ListIndent();
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");
builder.Writeln("MHTML");
builder.Writeln("Plain text");

// تجاوز مستوى القائمة مرة أخرى.
builder.ListFormat.ListOutdent();
builder.Writeln("Doing many other things!");

// إنهاء القائمة المرقمة.
builder.ListFormat.RemoveNumbers();

doc.Save(ArtifactsDir + "Lists.ApplyDefaultBulletsAndNumbers.docx");
```

### أنظر أيضا

* class [ListFormat](../)
* مساحة الاسم [Aspose.Words.Lists](../../listformat/)
* المجسم [Aspose.Words](../../../)


