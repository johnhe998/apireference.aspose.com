---
title: Class PlainTextDocument
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.PlainTextDocument فصل. يسمح باستخراج تمثيل نص عادي لمحتوى المستند.
type: docs
weight: 4190
url: /ar/net/aspose.words/plaintextdocument/
---
## PlainTextDocument class

يسمح باستخراج تمثيل نص عادي لمحتوى المستند.

```csharp
public class PlainTextDocument
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [PlainTextDocument](plaintextdocument/#constructor)(Stream) | إنشاء مستند نص عادي من دفق. يكتشف تنسيق الملف تلقائيًا. |
| [PlainTextDocument](plaintextdocument/#constructor_2)(string) | لإنشاء مستند نص عادي من ملف. يكتشف تنسيق الملف تلقائيًا. |
| [PlainTextDocument](plaintextdocument/#constructor_1)(Stream, LoadOptions) | إنشاء مستند نص عادي من دفق. يسمح بتحديد خيارات إضافية مثل كلمة مرور التشفير. |
| [PlainTextDocument](plaintextdocument/#constructor_3)(string, LoadOptions) | لإنشاء مستند نص عادي من ملف. يسمح بتحديد خيارات إضافية مثل كلمة مرور التشفير. |

## الخصائص

| اسم | وصف |
| --- | --- |
| [BuiltInDocumentProperties](../../aspose.words/plaintextdocument/builtindocumentproperties/) { get; } | يحصل[`BuiltInDocumentProperties`](./builtindocumentproperties/) من الوثيقة. |
| [CustomDocumentProperties](../../aspose.words/plaintextdocument/customdocumentproperties/) { get; } | يحصل[`CustomDocumentProperties`](./customdocumentproperties/) من الوثيقة. |
| [Text](../../aspose.words/plaintextdocument/text/) { get; } | الحصول على المحتوى النصي للمستند متسلسلًا كسلسلة. |

### أمثلة

يوضح كيفية تحميل محتويات مستند Microsoft Word بنص عادي.

```csharp
Document doc = new Document(); 
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "PlainTextDocument.Load.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.Load.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


