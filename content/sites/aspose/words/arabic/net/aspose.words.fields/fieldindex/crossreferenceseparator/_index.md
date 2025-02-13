---
title: FieldIndex.CrossReferenceSeparator
second_title: Aspose.Words لمراجع .NET API
description: FieldIndex ملكية. الحصول على أو تعيين تسلسل الأحرف المستخدم لفصل المراجع التبادلية والإدخالات الأخرى.
type: docs
weight: 30
url: /ar/net/aspose.words.fields/fieldindex/crossreferenceseparator/
---
## FieldIndex.CrossReferenceSeparator property

الحصول على أو تعيين تسلسل الأحرف المستخدم لفصل المراجع التبادلية والإدخالات الأخرى.

```csharp
public string CrossReferenceSeparator { get; set; }
```

### أمثلة

يوضح كيفية تحديد المراجع التبادلية في حقل INDEX.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء حقل INDEX الذي سيعرض إدخالاً لكل حقل XE موجود في المستند.
// سيعرض كل إدخال قيمة خاصية نص حقل XE على الجانب الأيسر ،
// ورقم الصفحة التي تحتوي على حقل XE على اليمين.
// سيجمع إدخال INDEX جميع حقول XE ذات القيم المتطابقة في خاصية "النص"
// في إدخال واحد بدلاً من إدخال إدخال لكل حقل XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// يمكننا تكوين حقل XE للحصول على إدخال INDEX الخاص به لعرض سلسلة بدلاً من رقم الصفحة.
// أولاً ، للإدخالات التي تستبدل رقم صفحة بسلسلة ،
// حدد فاصلًا مخصصًا بين قيمة خاصية Text لحقل XE والسلسلة.
index.CrossReferenceSeparator = ", see: ";

Assert.AreEqual(" INDEX  \\k \", see: \"", index.GetFieldCode());

// أدخل حقل XE ، والذي يقوم بإنشاء إدخال INDEX عادي يعرض رقم صفحة هذا الحقل ،
// ولا تستدعي قيمة CrossReferenceSeparator.
// سيعرض الإدخال الخاص بهذا الحقل XE "Apple، 2".
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Apple";

Assert.AreEqual(" XE  Apple", indexEntry.GetFieldCode());

// أدخل حقل XE آخر في الصفحة 3 وقم بتعيين قيمة للخاصية PageNumberReplacement.
// ستظهر هذه القيمة بدلاً من رقم الصفحة التي يوجد بها هذا الحقل ،
// وستظهر قيمة CrossReferenceSeparator للحقل INDEX أمامه.
// سيعرض الإدخال الخاص بهذا الحقل XE "الموز ، راجع: الفاكهة الاستوائية".
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Banana";
indexEntry.PageNumberReplacement = "Tropical fruit";

Assert.AreEqual(" XE  Banana \\t \"Tropical fruit\"", indexEntry.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.CrossReferenceSeparator.docx");
```

### أنظر أيضا

* class [FieldIndex](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldindex/)
* المجسم [Aspose.Words](../../../)


