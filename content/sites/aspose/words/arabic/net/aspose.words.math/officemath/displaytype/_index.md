---
title: OfficeMath.DisplayType
second_title: Aspose.Words لمراجع .NET API
description: OfficeMath ملكية. الحصول على / تعيين نوع تنسيق عرض Office Math الذي يمثل ما إذا كانت المعادلة تُعرض سطريًا مع النص أو يتم عرضها على السطر الخاص بها.
type: docs
weight: 10
url: /ar/net/aspose.words.math/officemath/displaytype/
---
## OfficeMath.DisplayType property

الحصول على / تعيين نوع تنسيق عرض Office Math الذي يمثل ما إذا كانت المعادلة تُعرض سطريًا مع النص أو يتم عرضها على السطر الخاص بها.

```csharp
public OfficeMathDisplayType DisplayType { get; set; }
```

### ملاحظات

نوع تنسيق العرض له تأثير لرياضيات Office ذات المستوى الأعلى فقط.

نوع تنسيق العرض الذي تم إرجاعه دائمًاInline لرياضيات Office المتداخلة.

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

* enum [OfficeMathDisplayType](../../officemathdisplaytype/)
* class [OfficeMath](../)
* مساحة الاسم [Aspose.Words.Math](../../officemath/)
* المجسم [Aspose.Words](../../../)


