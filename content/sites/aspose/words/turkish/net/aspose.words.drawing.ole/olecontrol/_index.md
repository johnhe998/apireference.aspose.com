---
title: Class OleControl
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.Ole.OleControl sınıf. OLE ActiveX denetimini temsil eder.
type: docs
weight: 1010
url: /tr/net/aspose.words.drawing.ole/olecontrol/
---
## OleControl class

OLE ActiveX denetimini temsil eder.

```csharp
public class OleControl
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| virtual [IsForms2OleControl](../../aspose.words.drawing.ole/olecontrol/isforms2olecontrol/) { get; } | Kontrol bir ise true döndürür[`Forms2OleControl`](../forms2olecontrol/) . |
| [Name](../../aspose.words.drawing.ole/olecontrol/name/) { get; } | ActiveX denetiminin adını alır. |

### Örnekler

ActiveX denetiminin özelliklerinin nasıl doğrulanacağını gösterir.

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

### Ayrıca bakınız

* ad alanı [Aspose.Words.Drawing.Ole](../../aspose.words.drawing.ole/)
* toplantı [Aspose.Words](../../)


