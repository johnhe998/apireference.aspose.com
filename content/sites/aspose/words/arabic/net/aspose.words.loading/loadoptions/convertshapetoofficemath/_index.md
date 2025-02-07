---
title: LoadOptions.ConvertShapeToOfficeMath
second_title: Aspose.Words لمراجع .NET API
description: LoadOptions ملكية. الحصول على أو تعيين ما إذا كان سيتم تحويل الأشكال باستخدام EquationXML إلى كائنات Office Math.
type: docs
weight: 40
url: /ar/net/aspose.words.loading/loadoptions/convertshapetoofficemath/
---
## LoadOptions.ConvertShapeToOfficeMath property

الحصول على أو تعيين ما إذا كان سيتم تحويل الأشكال باستخدام EquationXML إلى كائنات Office Math.

```csharp
public bool ConvertShapeToOfficeMath { get; set; }
```

### أمثلة

يوضح كيفية تحويل أشكال EquationXML إلى كائنات Office Math.

```csharp
LoadOptions loadOptions = new LoadOptions();

// استخدم هذه العلامة لتحديد ما إذا كنت تريد تحويل الأشكال بسمات EquationXML
// إلى كائنات Office Math ثم قم بتحميل المستند.
loadOptions.ConvertShapeToOfficeMath = isConvertShapeToOfficeMath;

Document doc = new Document(MyDir + "Math shapes.docx", loadOptions);

if (isConvertShapeToOfficeMath)
{
    Assert.AreEqual(16, doc.GetChildNodes(NodeType.Shape, true).Count);
    Assert.AreEqual(34, doc.GetChildNodes(NodeType.OfficeMath, true).Count);
}
else
{
    Assert.AreEqual(24, doc.GetChildNodes(NodeType.Shape, true).Count);
    Assert.AreEqual(0, doc.GetChildNodes(NodeType.OfficeMath, true).Count);
}
```

### أنظر أيضا

* class [LoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../loadoptions/)
* المجسم [Aspose.Words](../../../)


