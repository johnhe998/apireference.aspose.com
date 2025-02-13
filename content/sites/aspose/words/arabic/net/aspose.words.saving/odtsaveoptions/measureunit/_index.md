---
title: OdtSaveOptions.MeasureUnit
second_title: Aspose.Words لمراجع .NET API
description: OdtSaveOptions ملكية. يسمح بتحديد وحدات قياس لتطبيقها على محتوى المستند. القيمة الافتراضية هيCentimeters
type: docs
weight: 30
url: /ar/net/aspose.words.saving/odtsaveoptions/measureunit/
---
## OdtSaveOptions.MeasureUnit property

يسمح بتحديد وحدات قياس لتطبيقها على محتوى المستند. القيمة الافتراضية هيCentimeters

```csharp
public OdtSaveMeasureUnit MeasureUnit { get; set; }
```

### ملاحظات

يستخدم Open Office السنتيمترات عند تحديد الأطوال والعرض والتنسيقات الأخرى القابلة للقياس وخصائص المحتوى في المستندات بينما يستخدم MS Office البوصات .

### أمثلة

يوضح كيفية استخدام وحدات قياس مختلفة لتحديد معلمات النمط لمستند ODT محفوظ.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// عندما نقوم بتصدير المستند إلى .odt ، يمكننا استخدام كائن OdtSaveOptions لتعديل كيفية حفظ المستند.
// يمكننا تعيين خاصية "MeasureUnit" على "OdtSaveMeasureUnit.Centimeters"
// لتعريف محتوى مثل معلمات النمط باستخدام النظام المتري الذي يستخدمه Open Office. 
// يمكننا تعيين خاصية "MeasureUnit" على "OdtSaveMeasureUnit.Inches"
// لتعريف محتوى مثل معلمات النمط باستخدام النظام الإمبراطوري الذي يستخدمه Microsoft Word.
OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = odtSaveMeasureUnit
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### أنظر أيضا

* enum [OdtSaveMeasureUnit](../../odtsavemeasureunit/)
* class [OdtSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../odtsaveoptions/)
* المجسم [Aspose.Words](../../../)


