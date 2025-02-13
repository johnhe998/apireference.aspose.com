---
title: OleFormat.OleControl
second_title: Referencia de API de Aspose.Words para .NET
description: OleFormat propiedad. ObtieneOleControl objetos si este objeto OLE es un control ActiveX. De lo contrario esta propiedad es nula.
type: docs
weight: 60
url: /es/net/aspose.words.drawing/oleformat/olecontrol/
---
## OleFormat.OleControl property

Obtiene`OleControl` objetos si este objeto OLE es un control ActiveX. De lo contrario, esta propiedad es nula.

```csharp
public OleControl OleControl { get; }
```

### Ejemplos

Muestra cómo verificar las propiedades de un control ActiveX.

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

### Ver también

* class [OleControl](../../../aspose.words.drawing.ole/olecontrol/)
* class [OleFormat](../)
* espacio de nombres [Aspose.Words.Drawing](../../oleformat/)
* asamblea [Aspose.Words](../../../)


