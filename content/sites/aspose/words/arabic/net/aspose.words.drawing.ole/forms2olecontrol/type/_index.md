---
title: Forms2OleControl.Type
second_title: Aspose.Words لمراجع .NET API
description: Forms2OleControl ملكية. الحصول على عنصر تحكم 2.0 من النماذج .
type: docs
weight: 50
url: /ar/net/aspose.words.drawing.ole/forms2olecontrol/type/
---
## Forms2OleControl.Type property

الحصول على عنصر تحكم 2.0 من النماذج .

```csharp
public Forms2OleControlType Type { get; }
```

### أمثلة

يوضح كيفية التحقق من خصائص عنصر تحكم ActiveX.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");

Shape shape = (Shape) doc.GetChild(NodeType.Shape, 0, true);
OleControl oleControl = shape.OleFormat.OleControl;

Assert.AreEqual(null, oleControl.Name);

if (oleControl.IsForms2OleControl)
{
    Forms2OleControl checkBox = (Forms2OleControl) oleControl;
    Assert.AreEqual("Первый", checkBox.Caption);
    Assert.AreEqual("0", checkBox.Value);
    Assert.AreEqual(true, checkBox.Enabled);
    Assert.AreEqual(Forms2OleControlType.CheckBox, checkBox.Type);
    Assert.AreEqual(null, checkBox.ChildNodes);
}
```

### أنظر أيضا

* enum [Forms2OleControlType](../../forms2olecontroltype/)
* class [Forms2OleControl](../)
* مساحة الاسم [Aspose.Words.Drawing.Ole](../../forms2olecontrol/)
* المجسم [Aspose.Words](../../../)


