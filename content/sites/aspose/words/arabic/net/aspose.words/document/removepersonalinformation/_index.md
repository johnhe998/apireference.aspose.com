---
title: Document.RemovePersonalInformation
second_title: Aspose.Words لمراجع .NET API
description: Document ملكية. الحصول على أو تعيين علامة تشير إلى أن Microsoft Word سيزيل كافة معلومات المستخدم من التعليقات والمراجعات وخصائص المستند عند حفظ المستند.
type: docs
weight: 320
url: /ar/net/aspose.words/document/removepersonalinformation/
---
## Document.RemovePersonalInformation property

الحصول على أو تعيين علامة تشير إلى أن Microsoft Word سيزيل كافة معلومات المستخدم من التعليقات والمراجعات وخصائص المستند عند حفظ المستند.

```csharp
public bool RemovePersonalInformation { get; set; }
```

### أمثلة

يوضح كيفية تمكين إزالة المعلومات الشخصية أثناء الحفظ اليدوي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل بعض المحتوى مع المعلومات الشخصية.
doc.BuiltInDocumentProperties.Author = "John Doe";
doc.BuiltInDocumentProperties.Company = "Placeholder Inc.";

doc.StartTrackRevisions(doc.BuiltInDocumentProperties.Author, DateTime.Now);
builder.Write("Hello world!");
doc.StopTrackRevisions();

// هذه العلامة تعادل File - > خيارات - >. مركز التوثيق - >. إعدادات مركز التوثيق ... - >.
// خيارات الخصوصية - >. "إزالة المعلومات الشخصية من خصائص الملف عند الحفظ" في Microsoft Word.
doc.RemovePersonalInformation = saveWithoutPersonalInfo;

// لن يسري هذا الخيار أثناء عملية الحفظ التي تتم باستخدام Aspose.Words.
// ستتم إزالة البيانات الشخصية من وثيقتنا مع مجموعة العلم عندما نحفظها يدويًا باستخدام Microsoft Word.
doc.Save(ArtifactsDir + "Document.RemovePersonalInformation.docx");
doc = new Document(ArtifactsDir + "Document.RemovePersonalInformation.docx");

Assert.AreEqual(saveWithoutPersonalInfo, doc.RemovePersonalInformation);
Assert.AreEqual("John Doe", doc.BuiltInDocumentProperties.Author);
Assert.AreEqual("Placeholder Inc.", doc.BuiltInDocumentProperties.Company);
Assert.AreEqual("John Doe", doc.Revisions[0].Author);
```

### أنظر أيضا

* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


