---
title: FieldIndex.RunSubentriesOnSameLine
second_title: Aspose.Words لمراجع .NET API
description: FieldIndex ملكية. الحصول على أو تحديد ما إذا كان سيتم تشغيل المدخلات الفرعية في نفس السطر مثل الإدخال الرئيسي.
type: docs
weight: 140
url: /ar/net/aspose.words.fields/fieldindex/runsubentriesonsameline/
---
## FieldIndex.RunSubentriesOnSameLine property

الحصول على أو تحديد ما إذا كان سيتم تشغيل المدخلات الفرعية في نفس السطر مثل الإدخال الرئيسي.

```csharp
public bool RunSubentriesOnSameLine { get; set; }
```

### أمثلة

يوضح كيفية العمل مع المدخلات الفرعية في حقل INDEX.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء حقل INDEX الذي سيعرض إدخالاً لكل حقل XE موجود في المستند.
// سيعرض كل إدخال قيمة خاصية نص حقل XE على الجانب الأيسر ،
// ورقم الصفحة التي تحتوي على حقل XE على اليمين.
// سيجمع إدخال INDEX جميع حقول XE ذات القيم المتطابقة في خاصية "النص"
// في إدخال واحد بدلاً من إدخال إدخال لكل حقل XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);
index.PageNumberSeparator = ", see page ";
index.Heading = "A";

// حقول XE التي تحتوي على خاصية Text تصبح قيمتها عنوان إدخال INDEX.
// إذا كانت هذه القيمة تحتوي على جزأين من السلسلة مقسومين بنقطتين (سيتعامل إدخال INDEX مع :) المحدد ،
// الجزء الأول هو العنوان ، والجزء الثاني سيصبح العنوان الفرعي.
// يقوم حقل INDEX أولاً بتجميع الإدخالات أبجديًا ، ثم إذا كان هناك عدة حقول XE بنفس الشيء
// العناوين ، سيقوم الحقل INDEX بتجميعها بشكل فرعي حسب قيم هذه العناوين.
// يمكن أن يكون هناك طبقات تجميع فرعية متعددة ، اعتمادًا على عدد المرات
// يتم تقسيم خصائص النص لحقول XE على هذا النحو.
 // بشكل افتراضي ، ستنشئ مجموعة إدخال حقل INDEX سطرًا جديدًا لكل عنوان فرعي داخل هذه المجموعة.
// يمكننا ضبط علامة RunSubentriesOnSameLine على true للحفاظ على العنوان ،
// وكل عنوان فرعي للمجموعة في سطر واحد بدلاً من ذلك ، مما سيجعل حقل INDEX أكثر إحكاما.
index.RunSubentriesOnSameLine = runSubentriesOnTheSameLine;

if (runSubentriesOnTheSameLine)
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A \\r", index.GetFieldCode());
else
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A", index.GetFieldCode());

// أدخل حقلين XE ، كل منهما في صفحة جديدة ، وبنفس العنوان المسمى "العنوان 1" ،
// التي سيستخدمها الحقل INDEX لتجميعها.
// إذا كان RunSubentriesOnSameLine خاطئًا ، فسيقوم جدول INDEX بإنشاء ثلاثة أسطر:
// سطر واحد لعنوان التجميع "العنوان 1" ، وسطر آخر لكل عنوان فرعي.
// إذا كان RunSubentriesOnSameLine صحيحًا ، فسيقوم جدول INDEX بإنشاء سطر واحد
// الإدخال الذي يشمل العنوان وكل عنوان فرعي.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 1";

Assert.AreEqual(" XE  \"Heading 1:Subheading 1\"", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 2";

doc.UpdateFields();
doc.Save(ArtifactsDir + $"Field.INDEX.XE.Subheading.docx");
```

### أنظر أيضا

* class [FieldIndex](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldindex/)
* المجسم [Aspose.Words](../../../)


