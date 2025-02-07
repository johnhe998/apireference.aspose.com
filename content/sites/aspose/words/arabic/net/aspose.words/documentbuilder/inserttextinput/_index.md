---
title: DocumentBuilder.InsertTextInput
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. يُدرج حقل نموذج نصي في الموضع الحالي.
type: docs
weight: 450
url: /ar/net/aspose.words/documentbuilder/inserttextinput/
---
## DocumentBuilder.InsertTextInput method

يُدرج حقل نموذج نصي في الموضع الحالي.

```csharp
public FormField InsertTextInput(string name, TextFormFieldType type, string format, 
    string fieldValue, int maxLength)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| name | String | اسم حقل النموذج. يمكن أن تكون سلسلة فارغة. |
| type | TextFormFieldType | يحدد نوع حقل نموذج النص. |
| format | String | سلسلة التنسيق المستخدمة لتنسيق قيمة حقل النموذج. |
| fieldValue | String | النص الذي سيظهر في الحقل. |
| maxLength | Int32 | أقصى طول يمكن للمستخدم إدخاله في حقل النموذج. اضبط على صفر لطول غير محدود. |

### قيمة الإرجاع

عقدة حقل النموذج التي تم إدراجها للتو.

### ملاحظات

إذا قمت بتحديد اسم لحقل النموذج ، فسيتم إنشاء إشارة مرجعية تلقائيًا بنفس الاسم.

### أمثلة

يوضح كيفية إدراج حقل نموذج إدخال نص في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل نموذجًا يطالب المستخدم بإدخال نص.
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Enter your text here", 0);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTextInput.docx");
```

يوضح كيفية إدراج حقل نموذج إدخال نص.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please enter text here: ");

// أدخل حقل إدخال النص ، والذي سيسمح للمستخدم بالنقر فوقه وإدخال النص.
// تعيين نص عنصر نائب يمكن للمستخدم الكتابة فوقه وتمريره
// الحد الأقصى لطول النص 0 لعدم تطبيق أي حد على محتويات حقل النموذج.
builder.InsertTextInput("TextInput1", TextFormFieldType.Regular, "", "Placeholder text", 0);

// سيظهر حقل النموذج في شكل علامة html "إدخال" ، بنوع من "النص".
doc.Save(ArtifactsDir + "FormFields.TextInput.html");
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
* enum [TextFormFieldType](../../../aspose.words.fields/textformfieldtype/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


