---
title: FieldXE.EntryType
second_title: Aspose.Words لمراجع .NET API
description: FieldXE ملكية. الحصول على نوع إدخال فهرس أو تعيينه.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldxe/entrytype/
---
## FieldXE.EntryType property

الحصول على نوع إدخال فهرس أو تعيينه.

```csharp
public string EntryType { get; set; }
```

### أمثلة

يوضح كيفية إنشاء حقل INDEX ، ثم استخدام حقول XE لملئه بالإدخالات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء حقل INDEX الذي سيعرض إدخالاً لكل حقل XE موجود في المستند.
// سيعرض كل إدخال قيمة الخاصية Text لحقل XE على الجانب الأيسر
// والصفحة التي تحتوي على حقل XE على اليمين.
// إذا كانت حقول XE لها نفس القيمة في خاصية "النص" الخاصة بها ،
// سيجمعها الحقل INDEX في إدخال واحد.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// تكوين الحقل INDEX فقط لعرض حقول XE الموجودة داخل الحدود
// من إشارة مرجعية مسماة "MainBookmark" ، وخصائصها "EntryType" لها قيمة "A".
// بالنسبة لكل من الحقول INDEX و XE ، تستخدم الخاصية "EntryType" فقط الحرف الأول من قيمة السلسلة الخاصة بها.
index.BookmarkName = "MainBookmark";
index.EntryType = "A";

Assert.AreEqual(" INDEX  \\b MainBookmark \\f A", index.GetFieldCode());

// في صفحة جديدة ، ابدأ الإشارة المرجعية باسم يطابق القيمة
// من خاصية "BookmarkName" للحقل INDEX.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MainBookmark");

// سوف يلتقط حقل INDEX هذا الإدخال لأنه داخل الإشارة المرجعية ،
// ونوع الإدخال الخاص به يتطابق أيضًا مع نوع إدخال الحقل INDEX.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 1";
indexEntry.EntryType = "A";

Assert.AreEqual(" XE  \"Index entry 1\" \\f A", indexEntry.GetFieldCode());

// أدخل حقل XE لن يظهر في الفهرس لأن أنواع الإدخال غير متطابقة.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 2";
indexEntry.EntryType = "B";

// قم بإنهاء الإشارة المرجعية وأدخل حقل XE بعد ذلك.
// إنه من نفس نوع الحقل INDEX ، لكنه لن يظهر
// لأنه خارج حدود الإشارة المرجعية.
builder.EndBookmark("MainBookmark");
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 3";
indexEntry.EntryType = "A";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Filtering.docx");
```

### أنظر أيضا

* class [FieldXE](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldxe/)
* المجسم [Aspose.Words](../../../)


