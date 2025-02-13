---
title: Class Forms2OleControl
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.Ole.Forms2OleControl clase. Representa el control OLE de Microsoft Forms 2.0.
type: docs
weight: 980
url: /es/net/aspose.words.drawing.ole/forms2olecontrol/
---
## Forms2OleControl class

Representa el control OLE de Microsoft Forms 2.0.

```csharp
public abstract class Forms2OleControl : OleControl
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Caption](../../aspose.words.drawing.ole/forms2olecontrol/caption/) { get; } | Obtiene la propiedad Caption del control. El valor predeterminado es una cadena vacía. |
| [ChildNodes](../../aspose.words.drawing.ole/forms2olecontrol/childnodes/) { get; } | Obtiene la colección de controles secundarios inmediatos. |
| [Enabled](../../aspose.words.drawing.ole/forms2olecontrol/enabled/) { get; } | Devuelve verdadero si el control está en estado habilitado. |
| override [IsForms2OleControl](../../aspose.words.drawing.ole/forms2olecontrol/isforms2olecontrol/) { get; } |  |
| [Name](../../aspose.words.drawing.ole/olecontrol/name/) { get; } | Obtiene el nombre del control ActiveX. |
| [Type](../../aspose.words.drawing.ole/forms2olecontrol/type/) { get; } | Obtiene el tipo de control Forms 2.0. |
| [Value](../../aspose.words.drawing.ole/forms2olecontrol/value/) { get; } | Obtiene la propiedad Valor subyacente que a menudo representa el estado de control. Por ejemplo, el botón de opción marcado tiene el valor '1' mientras que no está marcado tiene '0'. El valor predeterminado es una cadena vacía. |

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

* class [OleControl](../olecontrol/)
* espacio de nombres [Aspose.Words.Drawing.Ole](../../aspose.words.drawing.ole/)
* asamblea [Aspose.Words](../../)


