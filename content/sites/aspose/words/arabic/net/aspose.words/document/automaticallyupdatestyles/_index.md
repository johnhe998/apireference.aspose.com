---
title: Document.AutomaticallyUpdateStyles
second_title: Aspose.Words لمراجع .NET API
description: Document ملكية. الحصول على علامة أو تعيينها تشير إلى ما إذا كانت الأنماط الموجودة في المستند قد تم تحديثها لمطابقة الأنماط الموجودة في القالب المرفق في كل مرة يتم فيها فتح المستند في MS Word.
type: docs
weight: 30
url: /ar/net/aspose.words/document/automaticallyupdatestyles/
---
## Document.AutomaticallyUpdateStyles property

الحصول على علامة أو تعيينها تشير إلى ما إذا كانت الأنماط الموجودة في المستند قد تم تحديثها لمطابقة الأنماط الموجودة في القالب المرفق في كل مرة يتم فيها فتح المستند في MS Word.

```csharp
public bool AutomaticallyUpdateStyles { get; set; }
```

### أمثلة

يوضح كيفية إرفاق قالب بمستند.

```csharp
Document doc = new Document();

// تأتي مستندات Microsoft Word بشكل افتراضي مع قالب مرفق يسمى "Normal.dotm".
// لا يوجد نموذج افتراضي لوثائق Aspose.Words الفارغة.
Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// إرفاق قالب ، ثم قم بتعيين العلم لتطبيق تغييرات النمط
// داخل القالب للأنماط في وثيقتنا.
doc.AttachedTemplate = MyDir + "Business brochure.dotx";
doc.AutomaticallyUpdateStyles = true;

doc.Save(ArtifactsDir + "Document.AutomaticallyUpdateStyles.docx");
```

يوضح كيفية تعيين قالب افتراضي للمستندات التي لا تحتوي على قوالب مرفقة.

```csharp
Document doc = new Document();

// تمكين التحديث التلقائي للنمط ، لكن لا تقم بإرفاق مستند نموذج.
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// نظرًا لعدم وجود مستند قالب ، لم يكن للمستند أي مكان لتعقب تغييرات النمط.
// استخدم كائن SaveOptions لتعيين قالب تلقائيًا
// إذا كان المستند الذي نحفظه لا يحتوي على واحد.
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### أنظر أيضا

* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


