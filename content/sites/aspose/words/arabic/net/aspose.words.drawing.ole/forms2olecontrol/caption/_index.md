---
title: Forms2OleControl.Caption
second_title: Aspose.Words لمراجع .NET API
description: Forms2OleControl ملكية. يحصل على خاصية التسمية التوضيحية للتحكم. القيمة الافتراضية هي سلسلة فارغة.
type: docs
weight: 10
url: /ar/net/aspose.words.drawing.ole/forms2olecontrol/caption/
---
## Forms2OleControl.Caption property

يحصل على خاصية التسمية التوضيحية للتحكم. القيمة الافتراضية هي سلسلة فارغة.

```csharp
public string Caption { get; }
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

* class [Forms2OleControl](../)
* مساحة الاسم [Aspose.Words.Drawing.Ole](../../forms2olecontrol/)
* المجسم [Aspose.Words](../../../)


