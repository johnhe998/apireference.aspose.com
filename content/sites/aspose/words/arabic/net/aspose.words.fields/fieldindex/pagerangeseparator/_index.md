---
title: FieldIndex.PageRangeSeparator
second_title: Aspose.Words لمراجع .NET API
description: FieldIndex ملكية. الحصول على أو تعيين تسلسل الأحرف المستخدم لفصل بداية نطاق الصفحات ونهايته.
type: docs
weight: 130
url: /ar/net/aspose.words.fields/fieldindex/pagerangeseparator/
---
## FieldIndex.PageRangeSeparator property

الحصول على أو تعيين تسلسل الأحرف المستخدم لفصل بداية نطاق الصفحات ونهايته.

```csharp
public string PageRangeSeparator { get; set; }
```

### أمثلة

يوضح كيفية تحديد الصفحات الممتدة لإشارة مرجعية كنطاق صفحات لإدخال حقل INDEX.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء حقل INDEX الذي سيعرض إدخالاً لكل حقل XE موجود في المستند.
// سيعرض كل إدخال قيمة خاصية نص حقل XE على الجانب الأيسر ،
// ورقم الصفحة التي تحتوي على حقل XE على اليمين.
// سيجمع إدخال INDEX جميع حقول XE ذات القيم المتطابقة في خاصية "النص"
// في إدخال واحد بدلاً من إدخال إدخال لكل حقل XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// بالنسبة لإدخالات INDEX التي تعرض نطاقات الصفحات ، يمكننا تحديد سلسلة فاصلة
// التي ستظهر بين رقم الصفحة الأولى ورقم الصفحة الأخيرة.
index.PageNumberSeparator = ", on page(s) ";
index.PageRangeSeparator = " to ";

Assert.AreEqual(" INDEX  \\e \", on page(s) \" \\g \" to \"", index.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "My entry";

// إذا قام حقل XE بتسمية إشارة مرجعية باستخدام خاصية PageRangeBookmarkName ،
// سيُظهر إدخال INDEX الخاص به نطاق الصفحات التي تمتد الإشارة المرجعية إليها
// بدلاً من رقم الصفحة التي تحتوي على الحقل XE.
indexEntry.PageRangeBookmarkName = "MyBookmark";

Assert.AreEqual(" XE  \"My entry\" \\r MyBookmark", indexEntry.GetFieldCode());
Assert.AreEqual("MyBookmark", indexEntry.PageRangeBookmarkName);

// أدخل إشارة مرجعية تبدأ في الصفحة 3 وتنتهي في الصفحة 5.
// سيعرض إدخال INDEX للحقل XE الذي يشير إلى هذه الإشارة المرجعية نطاق الصفحات هذا.
// في الجدول الخاص بنا ، سيعرض الإدخال INDEX "الإدخال الخاص بي ، في الصفحة (الصفحات) من 3 إلى 5".
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MyBookmark");
builder.Write("Start of MyBookmark");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.Write("End of MyBookmark");
builder.EndBookmark("MyBookmark");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.PageRangeBookmark.docx");
```

### أنظر أيضا

* class [FieldIndex](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldindex/)
* المجسم [Aspose.Words](../../../)


