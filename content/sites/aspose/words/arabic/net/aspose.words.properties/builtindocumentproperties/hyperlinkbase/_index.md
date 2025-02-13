---
title: BuiltInDocumentProperties.HyperlinkBase
second_title: Aspose.Words لمراجع .NET API
description: BuiltInDocumentProperties ملكية. تحديد السلسلة الأساسية المستخدمة لتقييم الارتباطات التشعبية النسبية في هذا المستند.
type: docs
weight: 120
url: /ar/net/aspose.words.properties/builtindocumentproperties/hyperlinkbase/
---
## BuiltInDocumentProperties.HyperlinkBase property

تحديد السلسلة الأساسية المستخدمة لتقييم الارتباطات التشعبية النسبية في هذا المستند.

```csharp
public string HyperlinkBase { get; set; }
```

### ملاحظات

Aspose.Words لا تستخدم هذه الخاصية.

### أمثلة

يوضح كيفية تخزين الجزء الأساسي من الارتباط التشعبي في خصائص المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل ارتباط تشعبي نسبي إلى مستند في نظام الملفات المحلي المسمى "Document.docx".
// سيؤدي النقر فوق الارتباط الموجود في Microsoft Word إلى فتح المستند المحدد ، إذا كان متاحًا.
builder.InsertHyperlink("Relative hyperlink", "Document.docx", false);

// هذا الارتباط نسبي. إذا لم يكن هناك "Document.docx" في نفس المجلد
// باعتباره المستند الذي يحتوي على هذا الارتباط ، سيتم كسر الارتباط.
Assert.False(File.Exists(ArtifactsDir + "Document.docx"));
doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.BrokenLink.docx");

// المستند الذي نحاول الارتباط به موجود في دليل مختلف عن ذلك الذي نخطط لحفظ المستند فيه.
// يمكننا إصلاح روابط مثل هذه عن طريق وضع اسم ملف مطلق في كل واحد. 
// بدلاً من ذلك ، يمكننا توفير ارتباط أساسي لكل ارتباط تشعبي باسم ملف نسبي
// ستعتمد على رابطها عندما نضغط عليها. 
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;
properties.HyperlinkBase = MyDir;

Assert.True(File.Exists(properties.HyperlinkBase + ((FieldHyperlink)doc.Range.Fields[0]).Address));

doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.WorkingLink.docx");
```

### أنظر أيضا

* class [BuiltInDocumentProperties](../)
* مساحة الاسم [Aspose.Words.Properties](../../builtindocumentproperties/)
* المجسم [Aspose.Words](../../../)


