---
title: DocumentProperty.ToByteArray
second_title: Aspose.Words لمراجع .NET API
description: DocumentProperty طريقة. إرجاع قيمة الخاصية كمصفوفة بايت.
type: docs
weight: 70
url: /ar/net/aspose.words.properties/documentproperty/tobytearray/
---
## DocumentProperty.ToByteArray method

إرجاع قيمة الخاصية كمصفوفة بايت.

```csharp
public byte[] ToByteArray()
```

### ملاحظات

يطرح استثناء إذا لم يكن نوع الخاصيةByteArray.

### أمثلة

يوضح كيفية إضافة صورة مصغرة إلى مستند نقوم بحفظه على هيئة Epub.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// إذا قمنا بحفظ مستند ، تحتوي خاصية "Thumbnail" الخاصة به على بيانات الصورة التي أضفناها ، مثل Epub ،
// القارئ الذي يفتح هذا المستند قد يعرض الصورة قبل الصفحة الأولى.
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

byte[] thumbnailBytes = File.ReadAllBytes(ImageDir + "Logo.jpg");
properties.Thumbnail = thumbnailBytes;

doc.Save(ArtifactsDir + "DocumentProperties.Thumbnail.epub");

// يمكننا استخراج الصورة المصغرة للمستند وحفظها في نظام الملفات المحلي.
DocumentProperty thumbnail = doc.BuiltInDocumentProperties["Thumbnail"];
File.WriteAllBytes(ArtifactsDir + "DocumentProperties.Thumbnail.gif", thumbnail.ToByteArray());
```

### أنظر أيضا

* class [DocumentProperty](../)
* مساحة الاسم [Aspose.Words.Properties](../../documentproperty/)
* المجسم [Aspose.Words](../../../)


