---
title: DocumentBuilder.PageSetup
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder ملكية. إرجاع كائن يمثل إعداد الصفحة الحالية وخصائص القسم.
type: docs
weight: 140
url: /ar/net/aspose.words/documentbuilder/pagesetup/
---
## DocumentBuilder.PageSetup property

إرجاع كائن يمثل إعداد الصفحة الحالية وخصائص القسم.

```csharp
public PageSetup PageSetup { get; }
```

### أمثلة

يوضح كيفية تطبيق إعدادات إعداد الصفحة وإعادتها إلى أقسام في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بتعديل خصائص إعداد الصفحة للقسم الحالي للمنشئ وإضافة نص.
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.VerticalAlignment = PageVerticalAlignment.Center;
builder.Writeln("This is the first section, which landscape oriented with vertically centered text.");

// إذا بدأنا قسمًا جديدًا باستخدام أداة إنشاء المستندات ،
// سيرث خصائص إعداد الصفحة الحالية للمنشئ.
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(Orientation.Landscape, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Center, doc.Sections[1].PageSetup.VerticalAlignment);

// يمكننا إعادة خصائص إعداد الصفحة إلى قيمها الافتراضية باستخدام طريقة "ClearFormatting".
builder.PageSetup.ClearFormatting();

Assert.AreEqual(Orientation.Portrait, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Top, doc.Sections[1].PageSetup.VerticalAlignment);

builder.Writeln("This is the second section, which is in default Letter paper size, portrait orientation and top alignment.");

doc.Save(ArtifactsDir + "PageSetup.ClearFormatting.docx");
```

### أنظر أيضا

* class [PageSetup](../../pagesetup/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


