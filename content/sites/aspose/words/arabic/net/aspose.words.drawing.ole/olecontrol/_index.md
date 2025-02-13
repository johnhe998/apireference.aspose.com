---
title: Class OleControl
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.Ole.OleControl فصل. يمثل عنصر تحكم OLE ActiveX.
type: docs
weight: 1010
url: /ar/net/aspose.words.drawing.ole/olecontrol/
---
## OleControl class

يمثل عنصر تحكم OLE ActiveX.

```csharp
public class OleControl
```

## الخصائص

| اسم | وصف |
| --- | --- |
| virtual [IsForms2OleControl](../../aspose.words.drawing.ole/olecontrol/isforms2olecontrol/) { get; } | إرجاع صحيح إذا كان عنصر التحكم[`Forms2OleControl`](../forms2olecontrol/) . |
| [Name](../../aspose.words.drawing.ole/olecontrol/name/) { get; } | الحصول على اسم عنصر تحكم ActiveX . |

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

* مساحة الاسم [Aspose.Words.Drawing.Ole](../../aspose.words.drawing.ole/)
* المجسم [Aspose.Words](../../)


