---
title: BuiltInDocumentProperties.Title
second_title: Aspose.Words لمراجع .NET API
description: BuiltInDocumentProperties ملكية. الحصول على عنوان المستند أو تحديده.
type: docs
weight: 290
url: /ar/net/aspose.words.properties/builtindocumentproperties/title/
---
## BuiltInDocumentProperties.Title property

الحصول على عنوان المستند أو تحديده.

```csharp
public string Title { get; set; }
```

### أمثلة

يوضح كيفية العمل مع خصائص المستند المضمنة في فئة "الوصف".

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

// فيما يلي أربع خصائص مضمنة للمستند تحتوي على حقول يمكنها عرض قيمها في نص المستند.
// 1 - خاصية "المؤلف" ، والتي يمكننا عرضها باستخدام حقل AUTHOR:
properties.Author = "John Doe";
builder.Write("Author:\t");
builder.InsertField(FieldType.FieldAuthor, true);

// 2 - خاصية "Title" ، والتي يمكننا عرضها باستخدام حقل TITLE:
properties.Title = "John's Document";
builder.Write("\nDoc title:\t");
builder.InsertField(FieldType.FieldTitle, true);

// 3 - خاصية "الموضوع" ، والتي يمكننا عرضها باستخدام حقل SUBJECT:
properties.Subject = "My subject";
builder.Write("\nSubject:\t");
builder.InsertField(FieldType.FieldSubject, true);

// 4 - خاصية "التعليقات" ، والتي يمكننا عرضها باستخدام حقل "التعليقات":
properties.Comments = $"This is {properties.Author}'s document about {properties.Subject}";
builder.Write("\nComments:\t\"");
builder.InsertField(FieldType.FieldComments, true);
builder.Write("\"");

// لا تحتوي الخاصية المضمنة في "الفئة" على حقل يمكنه عرض قيمته.
properties.Category = "My category";

// يمكننا تعيين كلمات رئيسية متعددة لمستند عن طريق فصل قيمة سلسلة خاصية "الكلمات الرئيسية" بفواصل منقوطة.
properties.Keywords = "Tag 1; Tag 2; Tag 3";

// يمكننا النقر بزر الماوس الأيمن فوق هذا المستند في مستكشف Windows والعثور على هذه الخصائص في "خصائص" - >; "تفاصيل".
// الخاصية المضمنة في "المؤلف" موجودة في مجموعة "الأصل" ، والآخرون في مجموعة "الوصف".
doc.Save(ArtifactsDir + "DocumentProperties.Description.docx");
```

### أنظر أيضا

* class [BuiltInDocumentProperties](../)
* مساحة الاسم [Aspose.Words.Properties](../../builtindocumentproperties/)
* المجسم [Aspose.Words](../../../)


