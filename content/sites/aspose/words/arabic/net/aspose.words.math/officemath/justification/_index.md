---
title: OfficeMath.Justification
second_title: Aspose.Words لمراجع .NET API
description: OfficeMath ملكية. Gets / Sets Office Math justification.
type: docs
weight: 30
url: /ar/net/aspose.words.math/officemath/justification/
---
## OfficeMath.Justification property

Gets / Sets Office Math justification.

```csharp
public OfficeMathJustification Justification { get; set; }
```

### ملاحظات

لا يمكن تعيين الضبط على Office Math بنوع تنسيق العرضInline.

لا يمكن تعيين الضبط المضمن على Office Math بنوع تنسيق العرضDisplay.

المقابلة[`DisplayType`](../displaytype/) يجب تعيينه قبل تعيين تبرير Office Math.

### أمثلة

يوضح كيفية تعيين تنسيق عرض الرياضيات في المكتب.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath) doc.GetChild(NodeType.OfficeMath, 0, true);

// تكون عُقد OfficeMath التابعة لعقد OfficeMath الأخرى مضمنة دائمًا.
// العقدة التي نعمل معها هي العقدة الأساسية لتغيير موقعها ونوع عرضها.
Assert.AreEqual(MathObjectType.OMathPara, officeMath.MathObjectType);
Assert.AreEqual(NodeType.OfficeMath, officeMath.NodeType);
Assert.AreEqual(officeMath.ParentNode, officeMath.ParentParagraph);

// تستخدم تنسيقات OOXML و WML الخاصية "EquationXmlEncoding".
Assert.IsNull(officeMath.EquationXmlEncoding);

// تغيير الموقع ونوع العرض لعقدة OfficeMath.
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

doc.Save(ArtifactsDir + "Shape.OfficeMath.docx");
```

### أنظر أيضا

* enum [OfficeMathJustification](../../officemathjustification/)
* class [OfficeMath](../)
* مساحة الاسم [Aspose.Words.Math](../../officemath/)
* المجسم [Aspose.Words](../../../)


