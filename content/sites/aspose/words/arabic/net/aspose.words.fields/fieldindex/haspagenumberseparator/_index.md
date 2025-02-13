---
title: FieldIndex.HasPageNumberSeparator
second_title: Aspose.Words لمراجع .NET API
description: FieldIndex ملكية. يحصل على قيمة تشير إلى ما إذا كان فاصل رقم الصفحة قد تم تجاوزه من خلال كود الحقل.
type: docs
weight: 50
url: /ar/net/aspose.words.fields/fieldindex/haspagenumberseparator/
---
## FieldIndex.HasPageNumberSeparator property

يحصل على قيمة تشير إلى ما إذا كان فاصل رقم الصفحة قد تم تجاوزه من خلال كود الحقل.

```csharp
public bool HasPageNumberSeparator { get; }
```

### أمثلة

يوضح كيفية تحرير فاصل رقم الصفحة في حقل INDEX.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء حقل INDEX الذي سيعرض إدخالاً لكل حقل XE موجود في المستند.
// سيعرض كل إدخال قيمة خاصية نص حقل XE على الجانب الأيسر ،
// ورقم الصفحة التي تحتوي على حقل XE على اليمين.
// سيقوم إدخال INDEX بتجميع حقول XE ذات القيم المتطابقة في خاصية "النص"
// في إدخال واحد بدلاً من إدخال إدخال لكل حقل XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// إذا كان حقل INDEX الخاص بنا يحتوي على إدخال لمجموعة من حقول XE ،
// سيعرض هذا الإدخال رقم كل صفحة تحتوي على حقل XE ينتمي إلى هذه المجموعة.
// يمكننا تعيين فواصل مخصصة لتخصيص مظهر أرقام الصفحات هذه.
index.PageNumberSeparator = ", on page(s) ";
index.PageNumberListSeparator = " & ";

Assert.AreEqual(" INDEX  \\e \", on page(s) \" \\l \" & \"", index.GetFieldCode());
Assert.True(index.HasPageNumberSeparator);

// بعد إدخال حقول XE هذه ، سيعرض حقل INDEX "الإدخال الأول ، في الصفحة (الصفحات) 2 & 3 & 4".
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

Assert.AreEqual(" XE  \"First entry\"", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "First entry";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.PageNumberList.docx");
```

### أنظر أيضا

* class [FieldIndex](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldindex/)
* المجسم [Aspose.Words](../../../)


