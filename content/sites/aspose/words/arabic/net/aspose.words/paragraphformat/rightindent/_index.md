---
title: ParagraphFormat.RightIndent
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. الحصول على أو تعيين القيمة بالنقاط التي تمثل المسافة البادئة اليمنى للفقرة .
type: docs
weight: 260
url: /ar/net/aspose.words/paragraphformat/rightindent/
---
## ParagraphFormat.RightIndent property

الحصول على أو تعيين القيمة (بالنقاط) التي تمثل المسافة البادئة اليمنى للفقرة .

```csharp
public double RightIndent { get; set; }
```

### أمثلة

يوضح كيفية تكوين تنسيق الفقرة لإنشاء نص خارج المركز.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// توسيط كل النص الذي يكتبه منشئ المستندات ، وقم بإعداد المسافات البادئة.
// سيُنشئ تكوين المسافة البادئة أدناه نصًا غير متماثل على الصفحة.
// "المركز" الذي نقوم بمحاذاة النص إليه سيكون منتصف نص النص ، وليس منتصف الصفحة.
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.Alignment = ParagraphAlignment.Center;
paragraphFormat.LeftIndent = 100;
paragraphFormat.RightIndent = 50;
paragraphFormat.SpaceAfter = 25;

builder.Writeln(
    "This paragraph demonstrates how left and right indentation affects word wrapping.");
builder.Writeln(
    "The space between the above paragraph and this one depends on the DocumentBuilder's paragraph format.");

doc.Save(ArtifactsDir + "DocumentBuilder.SetParagraphFormatting.docx");
```

### أنظر أيضا

* class [ParagraphFormat](../)
* مساحة الاسم [Aspose.Words](../../paragraphformat/)
* المجسم [Aspose.Words](../../../)


