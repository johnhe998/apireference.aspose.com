---
title: Font.Italic
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. True إذا تم تنسيق الخط على أنه مائل.
type: docs
weight: 160
url: /ar/net/aspose.words/font/italic/
---
## Font.Italic property

True إذا تم تنسيق الخط على أنه مائل.

```csharp
public bool Italic { get; set; }
```

### أمثلة

يوضح كيفية كتابة نص مائل باستخدام أداة إنشاء المستندات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 36;
builder.Font.Italic = true;
builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "Font.Italic.docx");
```

### أنظر أيضا

* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


