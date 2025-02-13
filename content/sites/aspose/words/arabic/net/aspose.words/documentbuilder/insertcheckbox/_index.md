---
title: DocumentBuilder.InsertCheckBox
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. يُدرج حقل نموذج خانة اختيار في الموضع الحالي.
type: docs
weight: 270
url: /ar/net/aspose.words/documentbuilder/insertcheckbox/
---
## InsertCheckBox(string, bool, int) {#insertcheckbox_1}

يُدرج حقل نموذج خانة اختيار في الموضع الحالي.

```csharp
public FormField InsertCheckBox(string name, bool checkedValue, int size)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| name | String | اسم حقل النموذج. يمكن أن تكون سلسلة فارغة. سيتم قطع القيمة التي تزيد عن 20 حرفًا. |
| checkedValue | Boolean | حالة التحقق من حقل نموذج مربع الاختيار. |
| size | Int32 | يحدد حجم خانة الاختيار بالنقاط. حدد 0 لـ MS Word لحساب حجم مربع الاختيار تلقائيًا. |

### قيمة الإرجاع

عقدة حقل النموذج التي تم إدراجها للتو.

### ملاحظات

إذا قمت بتحديد اسم لحقل النموذج ، فسيتم إنشاء إشارة مرجعية تلقائيًا بنفس الاسم.

### أمثلة

يوضح كيفية إدراج مربعات الاختيار في المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل مربعات الاختيار ذات الأحجام المختلفة والحالات الافتراضية المحددة.
builder.Write("Unchecked check box of a default size: ");
builder.InsertCheckBox(string.Empty, false, false, 0);
builder.InsertParagraph();

builder.Write("Large checked check box: ");
builder.InsertCheckBox("CheckBox_Default", true, true, 50);
builder.InsertParagraph();

// تحتوي حقول النموذج على حد أقصى لطول الاسم يبلغ 20 حرفًا.
builder.Write("Very large checked check box: ");
builder.InsertCheckBox("CheckBox_OnlyCheckedValue", true, 100);

Assert.AreEqual("CheckBox_OnlyChecked", doc.Range.FormFields[2].Name);

// يمكننا التفاعل مع مربعات الاختيار هذه في Microsoft Word بالنقر المزدوج عليها.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertCheckBox.docx");
```

### أنظر أيضا

* class [FormField](../../../aspose.words.fields/formfield/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)

---

## InsertCheckBox(string, bool, bool, int) {#insertcheckbox}

يُدرج حقل نموذج خانة اختيار في الموضع الحالي.

```csharp
public FormField InsertCheckBox(string name, bool defaultValue, bool checkedValue, int size)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| name | String | اسم حقل النموذج. يمكن أن تكون سلسلة فارغة. سيتم قطع القيمة التي تزيد عن 20 حرفًا. |
| defaultValue | Boolean | القيمة الافتراضية لحقل نموذج مربع الاختيار. |
| checkedValue | Boolean | الحالة المحددة الحالية لحقل نموذج مربع الاختيار. |
| size | Int32 | يحدد حجم خانة الاختيار بالنقاط. حدد 0 لـ MS Word لحساب حجم مربع الاختيار تلقائيًا. |

### قيمة الإرجاع

عقدة حقل النموذج التي تم إدراجها للتو.

### ملاحظات

إذا قمت بتحديد اسم لحقل النموذج ، فسيتم إنشاء إشارة مرجعية تلقائيًا بنفس الاسم.

### أمثلة

يوضح كيفية إدراج مربعات الاختيار في المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل مربعات الاختيار ذات الأحجام المختلفة والحالات الافتراضية المحددة.
builder.Write("Unchecked check box of a default size: ");
builder.InsertCheckBox(string.Empty, false, false, 0);
builder.InsertParagraph();

builder.Write("Large checked check box: ");
builder.InsertCheckBox("CheckBox_Default", true, true, 50);
builder.InsertParagraph();

// تحتوي حقول النموذج على حد أقصى لطول الاسم يبلغ 20 حرفًا.
builder.Write("Very large checked check box: ");
builder.InsertCheckBox("CheckBox_OnlyCheckedValue", true, 100);

Assert.AreEqual("CheckBox_OnlyChecked", doc.Range.FormFields[2].Name);

// يمكننا التفاعل مع مربعات الاختيار هذه في Microsoft Word بالنقر المزدوج عليها.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertCheckBox.docx");
```

### أنظر أيضا

* class [FormField](../../../aspose.words.fields/formfield/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


