---
title: StyleCollection.Item
second_title: Aspose.Words لمراجع .NET API
description: StyleCollection ملكية. الحصول على نمط بالاسم أو الاسم المستعار .
type: docs
weight: 50
url: /ar/net/aspose.words/stylecollection/item/
---
## StyleCollection indexer (1 of 3)

الحصول على نمط بالاسم أو الاسم المستعار .

```csharp
public Style this[string name] { get; }
```

### ملاحظات

حساس لحالة الأحرف ، يتم إرجاع قيمة فارغة إذا لم يتم العثور على النمط الذي يحمل الاسم المحدد.

إذا كان هذا اسمًا باللغة الإنجليزية لنمط مدمج غير موجود بعد ، فقم بإنشائه تلقائيًا.

### أمثلة

يظهر وقت إعادة حساب تخطيط الصفحة للمستند.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// حفظ مستند إلى ملف PDF أو في صورة أو الطباعة لأول مرة سيتم تلقائيًا
// تخزين تخطيط المستند مؤقتًا داخل صفحاته.
doc.Save(ArtifactsDir + "Document.UpdatePageLayout.1.pdf");

// قم بتعديل المستند بطريقة ما.
doc.Styles["Normal"].Font.Size = 6;
doc.Sections[0].PageSetup.Orientation = Aspose.Words.Orientation.Landscape;

 // في الإصدار الحالي من Aspose.Words ، لا يؤدي تعديل المستند إلى إعادة البناء تلقائيًا
// تخطيط الصفحة المخبأة. إذا كنا نرغب في التخطيط المخبأ
// للبقاء محدثًا ، سنحتاج إلى تحديثه يدويًا.
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Document.UpdatePageLayout.2.pdf");
```

### أنظر أيضا

* class [Style](../../style/)
* class [StyleCollection](../)
* مساحة الاسم [Aspose.Words](../../stylecollection/)
* المجسم [Aspose.Words](../../../)

---

## StyleCollection indexer (2 of 3)

الحصول على نمط مضمن بواسطة المعرف المستقل المحلي الخاص به.

```csharp
public Style this[StyleIdentifier sti] { get; }
```

| معامل | وصف |
| --- | --- |
| sti | أ[`StyleIdentifier`](../../styleidentifier/) القيمة التي تحدد النمط المضمن لاسترداده. |

### ملاحظات

عند الوصول إلى نمط غير موجود بعد ، يقوم بإنشائه تلقائيًا.

### أمثلة

يوضح كيفية إضافة نمط إلى مجموعة أنماط المستند.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// تعيين المعلمات الافتراضية للأنماط الجديدة التي قد نضيفها لاحقًا إلى هذه المجموعة.
styles.DefaultFont.Name = "Courier New";

// إذا أضفنا نمطًا من "StyleType.Paragraph" ، فستطبق المجموعة قيم
// الخاصية "DefaultParagraphFormat" الخاصة بها إلى خاصية "تنسيق ParagraphFormat" الخاصة بالنمط.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// أضف نمطًا ، ثم تحقق من أنه يحتوي على الإعدادات الافتراضية.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### أنظر أيضا

* class [Style](../../style/)
* enum [StyleIdentifier](../../styleidentifier/)
* class [StyleCollection](../)
* مساحة الاسم [Aspose.Words](../../stylecollection/)
* المجسم [Aspose.Words](../../../)

---

## StyleCollection indexer (3 of 3)

الحصول على نمط حسب الفهرس .

```csharp
public Style this[int index] { get; }
```

### أمثلة

يوضح كيفية إضافة نمط إلى مجموعة أنماط المستند.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// تعيين المعلمات الافتراضية للأنماط الجديدة التي قد نضيفها لاحقًا إلى هذه المجموعة.
styles.DefaultFont.Name = "Courier New";

// إذا أضفنا نمطًا من "StyleType.Paragraph" ، فستطبق المجموعة قيم
// الخاصية "DefaultParagraphFormat" الخاصة بها إلى خاصية "تنسيق ParagraphFormat" الخاصة بالنمط.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// أضف نمطًا ، ثم تحقق من أنه يحتوي على الإعدادات الافتراضية.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### أنظر أيضا

* class [Style](../../style/)
* class [StyleCollection](../)
* مساحة الاسم [Aspose.Words](../../stylecollection/)
* المجسم [Aspose.Words](../../../)


