---
title: OfficeMath.GetMathRenderer
second_title: Aspose.Words لمراجع .NET API
description: OfficeMath طريقة. إنشاء وإرجاع كائن يمكن استخدامه لتحويل هذه المعادلة إلى صورة.
type: docs
weight: 80
url: /ar/net/aspose.words.math/officemath/getmathrenderer/
---
## OfficeMath.GetMathRenderer method

إنشاء وإرجاع كائن يمكن استخدامه لتحويل هذه المعادلة إلى صورة.

```csharp
public OfficeMathRenderer GetMathRenderer()
```

### قيمة الإرجاع

كائن العارض لهذه المعادلة.

### ملاحظات

تستدعي هذه الطريقة فقط[`OfficeMathRenderer`](../../../aspose.words.rendering/officemathrenderer/)المُنشئ ويمرر هذا الكائن كمعامل.

### أمثلة

يوضح كيفية تحويل كائن Office Math إلى ملف صورة في نظام الملفات المحلي.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// قم بإنشاء كائن "ImageSaveOptions" لتمريره إلى طريقة "Save" لتعديل طريقة عرض العقدة
// كيف يعرض عقدة OfficeMath في صورة.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// اضبط خاصية "Scale" على 5 لجعل الكائن خمسة أضعاف حجمه الأصلي.
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

### أنظر أيضا

* class [OfficeMathRenderer](../../../aspose.words.rendering/officemathrenderer/)
* class [OfficeMath](../)
* مساحة الاسم [Aspose.Words.Math](../../officemath/)
* المجسم [Aspose.Words](../../../)


