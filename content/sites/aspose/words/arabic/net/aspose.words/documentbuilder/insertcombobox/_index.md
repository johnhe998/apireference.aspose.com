---
title: DocumentBuilder.InsertComboBox
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. يتم إدراج حقل نموذج مربع تحرير وسرد في الموضع الحالي.
type: docs
weight: 280
url: /ar/net/aspose.words/documentbuilder/insertcombobox/
---
## DocumentBuilder.InsertComboBox method

يتم إدراج حقل نموذج مربع تحرير وسرد في الموضع الحالي.

```csharp
public FormField InsertComboBox(string name, string[] items, int selectedIndex)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| name | String | اسم حقل النموذج. يمكن أن تكون سلسلة فارغة. سيتم قطع القيمة التي تزيد عن 20 حرفًا. |
| items | String[] | عناصر ComboBox. الحد الأقصى 25 قطعة. |
| selectedIndex | Int32 | فهرس العنصر المحدد في ComboBox. |

### قيمة الإرجاع

عقدة حقل النموذج التي تم إدراجها للتو.

### ملاحظات

إذا قمت بتحديد اسم لحقل النموذج ، فسيتم إنشاء إشارة مرجعية تلقائيًا بنفس الاسم.

### أمثلة

يوضح كيفية إدراج حقل نموذج مربع تحرير وسرد في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل نموذجًا يطالب المستخدم باختيار أحد العناصر من القائمة.
builder.Write("Pick a fruit: ");
string[] items = { "Apple", "Banana", "Cherry" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertComboBox.docx");
```

يوضح كيفية إنشاء حقول النموذج.

```csharp
DocumentBuilder builder = new DocumentBuilder();

// حقول النموذج هي كائنات في المستند يمكن للمستخدم التفاعل معها من خلال مطالبته بإدخال القيم.
// يمكننا إنشاؤها باستخدام أداة إنشاء المستندات ، وفيما يلي طريقتان للقيام بذلك.
// 1 - الإدخال الأساسي للنص:
builder.InsertTextInput("My text input", TextFormFieldType.Regular, 
    "", "Enter your name here", 30);

// 2 - مربع تحرير وسرد مع نص موجه ومجموعة من القيم الممكنة:
string[] items =
{
    "-- Select your favorite footwear --", "Sneakers", "Oxfords", "Flip-flops", "Other"
};

builder.InsertParagraph();
builder.InsertComboBox("My combo box", items, 0);

builder.Document.Save(ArtifactsDir + "DocumentBuilder.CreateForm.docx");
```

### أنظر أيضا

* class [FormField](../../../aspose.words.fields/formfield/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


