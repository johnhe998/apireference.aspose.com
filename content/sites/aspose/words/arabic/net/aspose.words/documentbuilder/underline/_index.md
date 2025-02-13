---
title: DocumentBuilder.Underline
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder ملكية. الحصول على / مجموعات نوع التسطير للخط الحالي.
type: docs
weight: 170
url: /ar/net/aspose.words/documentbuilder/underline/
---
## DocumentBuilder.Underline property

الحصول على / مجموعات نوع التسطير للخط الحالي.

```csharp
public Underline Underline { get; set; }
```

### أمثلة

يوضح كيفية تنسيق النص الذي تم إدراجه بواسطة منشئ المستندات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Underline = Underline.Dash;
builder.Font.Color = Color.Blue;
builder.Font.Size = 32;

// يطبق المنشئ التنسيق على فقرته الحالية وأي نص جديد يضيفه بعد ذلك.
builder.Writeln("Large, blue, and underlined text.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertUnderline.docx");
```

### أنظر أيضا

* enum [Underline](../../underline/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


