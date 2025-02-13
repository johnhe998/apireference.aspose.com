---
title: OdtSaveOptions.IsStrictSchema11
second_title: Aspose.Words لمراجع .NET API
description: OdtSaveOptions ملكية. يحدد ما إذا كان يجب أن يتوافق التصدير مع مواصفات ODT 1.1 بشكل صارم. OOo 3.0 يعرض الملفات بشكل صحيح عندما تحتوي على عناصر وسمات ODT 1.2. استخدم false لهذا الغرض  أو true للتوافق الصارم مع المواصفات 1.1. القيمة الافتراضية هي خاطئة .
type: docs
weight: 20
url: /ar/net/aspose.words.saving/odtsaveoptions/isstrictschema11/
---
## OdtSaveOptions.IsStrictSchema11 property

يحدد ما إذا كان يجب أن يتوافق التصدير مع مواصفات ODT 1.1 بشكل صارم. OOo 3.0 يعرض الملفات بشكل صحيح عندما تحتوي على عناصر وسمات ODT 1.2. استخدم "false" لهذا الغرض ، أو "true" للتوافق الصارم مع المواصفات 1.1. القيمة الافتراضية هي **خاطئة** .

```csharp
public bool IsStrictSchema11 { get; set; }
```

### أمثلة

يوضح كيفية جعل مستند محفوظ يتوافق مع مخطط ODT أقدم.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = OdtSaveMeasureUnit.Centimeters,
    IsStrictSchema11 = exportToOdt11Specs
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### أنظر أيضا

* class [OdtSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../odtsaveoptions/)
* المجسم [Aspose.Words](../../../)


