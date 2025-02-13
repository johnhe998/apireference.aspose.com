---
title: ToaCategories.Item
second_title: Aspose.Words لمراجع .NET API
description: ToaCategories ملكية. الحصول على أو تحديد عنوان الفئة حسب رقم الفئة.
type: docs
weight: 30
url: /ar/net/aspose.words.fields/toacategories/item/
---
## ToaCategories indexer

الحصول على أو تحديد عنوان الفئة حسب رقم الفئة.

```csharp
public string this[int number] { get; set; }
```

### أمثلة

يوضح كيفية تحديد مجموعة من الفئات لحقول TOA.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// يمكن لحقول TOA تصفية إدخالاتها حسب الفئات المحددة في هذه المجموعة.
ToaCategories toaCategories = new ToaCategories();
doc.FieldOptions.ToaCategories = toaCategories;

// تأتي هذه المجموعة من الفئات بقيم افتراضية ، يمكننا استبدالها بقيم مخصصة.
Assert.AreEqual("Cases", toaCategories[1]);
Assert.AreEqual("Statutes", toaCategories[2]);

toaCategories[1] = "My Category 1";
toaCategories[2] = "My Category 2";

// يمكننا دائمًا الوصول إلى القيم الافتراضية عبر هذه المجموعة.
Assert.AreEqual("Cases", ToaCategories.DefaultCategories[1]);
Assert.AreEqual("Statutes", ToaCategories.DefaultCategories[2]);

// أدخل 2 حقلي TOA. تقوم حقول TOA بإنشاء إدخال لكل حقل TA في المستند.
// استخدم مفتاح التبديل "\ c" لتحديد فهرس فئة من مجموعتنا.
// باستخدام رمز التبديل هذا ، لن يلتقط حقل TOA سوى الإدخالات من حقول TA التي
// يحتوي أيضًا على مفتاح تبديل "\ c" مع فهرس فئة مطابق. سيعرض كل حقل TOA أيضًا
// اسم الفئة التي يشير إليها التبديل "\ c".
builder.InsertField("TOA \\c 1 \\h", null);
builder.InsertField("TOA \\c 2 \\h", null);
builder.InsertBreak(BreakType.PageBreak);

// أدخل إدخالات TOA عبر فئتين. سيحصل حقل TOA الأول لدينا على إدخال واحد ،
// من حقل TA الثاني الذي يشير تبديله "\ c" أيضًا إلى الفئة الأولى.
// سيحتوي حقل TOA الثاني على إدخالين من حقلي TA الآخرين.
builder.InsertField("TA \\c 2 \\l \"entry 1\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 1 \\l \"entry 2\"");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertField("TA \\c 2 \\l \"entry 3\"");

doc.UpdateFields();
doc.Save(ArtifactsDir + "FieldOptions.TOA.Categories.docx");
```

### أنظر أيضا

* class [ToaCategories](../)
* مساحة الاسم [Aspose.Words.Fields](../../toacategories/)
* المجسم [Aspose.Words](../../../)


