---
title: Enum OdtSaveMeasureUnit
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.OdtSaveMeasureUnit تعداد. وحدات قياس محددة لتطبيقها على محتوى مستند قابل للقياس مثل الشكل والعرض وغير ذلك أثناء الحفظ.
type: docs
weight: 5040
url: /ar/net/aspose.words.saving/odtsavemeasureunit/
---
## OdtSaveMeasureUnit enumeration

وحدات قياس محددة لتطبيقها على محتوى مستند قابل للقياس مثل الشكل والعرض وغير ذلك أثناء الحفظ.

```csharp
public enum OdtSaveMeasureUnit
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Centimeters | `0` | يحدد أن محتوى المستند يتم حفظه باستخدام سنتيمترات. |
| Inches | `1` | تحديد أن محتوى المستند يتم حفظه باستخدام البوصة . |

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

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


