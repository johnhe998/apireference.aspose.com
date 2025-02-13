---
title: FieldXE.Yomi
second_title: Aspose.Words لمراجع .NET API
description: FieldXE ملكية. الحصول على أو تعيين yomi الحرف الصوتي الأول لفهارس الفرز لمدخل الفهرس
type: docs
weight: 80
url: /ar/net/aspose.words.fields/fieldxe/yomi/
---
## FieldXE.Yomi property

الحصول على أو تعيين yomi (الحرف الصوتي الأول لفهارس الفرز) لمدخل الفهرس

```csharp
public string Yomi { get; set; }
```

### أمثلة

يوضح كيفية فرز إدخالات حقل INDEX صوتيًا.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء حقل INDEX الذي سيعرض إدخالاً لكل حقل XE موجود في المستند.
// سيعرض كل إدخال قيمة خاصية نص حقل XE على الجانب الأيسر ،
// ورقم الصفحة التي تحتوي على حقل XE على اليمين.
// سيجمع إدخال INDEX جميع حقول XE ذات القيم المتطابقة في خاصية "النص"
// في إدخال واحد بدلاً من إدخال إدخال لكل حقل XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// يقوم جدول INDEX تلقائيًا بفرز إدخالاته حسب قيم خصائص النص الخاصة بهم بترتيب أبجدي.
// اضبط جدول INDEX لفرز الإدخالات صوتيًا باستخدام Hiragana بدلاً من ذلك.
index.UseYomi = sortEntriesUsingYomi;

if (sortEntriesUsingYomi)
    Assert.AreEqual(" INDEX  \\y", index.GetFieldCode());
else
    Assert.AreEqual(" INDEX ", index.GetFieldCode());

// أدخل 4 حقول XE ، والتي ستظهر كمدخلات في جدول محتويات الحقل INDEX.
// قد تحتوي خاصية "النص" على تهجئة كلمة بلغة كانجي ، والتي قد يكون نطقها غامضًا ،
// بينما ستتهجى نسخة "يومي" من الكلمة بالضبط كيف يتم نطقها باستخدام هيراغانا.
// إذا قمنا بتعيين حقل INDEX الخاص بنا لاستخدام Yomi ، فسيتم فرز هذه الإدخالات
// بقيمة خصائص Yomi الخاصة بهم ، بدلاً من قيمهم النصية.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "愛子";
indexEntry.Yomi = "あ";

Assert.AreEqual(" XE  愛子 \\y あ", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "明美";
indexEntry.Yomi = "あ";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "恵美";
indexEntry.Yomi = "え";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "愛美";
indexEntry.Yomi = "え";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Yomi.docx");
```

### أنظر أيضا

* class [FieldXE](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldxe/)
* المجسم [Aspose.Words](../../../)


