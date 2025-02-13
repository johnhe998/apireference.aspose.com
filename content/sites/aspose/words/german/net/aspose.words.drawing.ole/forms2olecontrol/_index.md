---
title: Class Forms2OleControl
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.Ole.Forms2OleControl klas. Stellt Microsoft Forms 2.0 OLESteuerelement dar.
type: docs
weight: 980
url: /de/net/aspose.words.drawing.ole/forms2olecontrol/
---
## Forms2OleControl class

Stellt Microsoft Forms 2.0 OLE-Steuerelement dar.

```csharp
public abstract class Forms2OleControl : OleControl
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Caption](../../aspose.words.drawing.ole/forms2olecontrol/caption/) { get; } | Ruft die Caption-Eigenschaft des Steuerelements ab. Der Standardwert ist eine leere Zeichenfolge. |
| [ChildNodes](../../aspose.words.drawing.ole/forms2olecontrol/childnodes/) { get; } | Ruft Sammlung von unmittelbar untergeordneten Steuerelementen ab. |
| [Enabled](../../aspose.words.drawing.ole/forms2olecontrol/enabled/) { get; } | Gibt „true“ zurück, wenn sich die Steuerung im aktivierten Zustand befindet. |
| override [IsForms2OleControl](../../aspose.words.drawing.ole/forms2olecontrol/isforms2olecontrol/) { get; } |  |
| [Name](../../aspose.words.drawing.ole/olecontrol/name/) { get; } | Ruft den Namen des ActiveX-Steuerelements ab. |
| [Type](../../aspose.words.drawing.ole/forms2olecontrol/type/) { get; } | Ruft den Typ des Forms 2.0-Steuerelements ab. |
| [Value](../../aspose.words.drawing.ole/forms2olecontrol/value/) { get; } | Ruft die zugrunde liegende Value-Eigenschaft ab, die häufig den Steuerungsstatus darstellt. Beispielsweise hat die aktivierte Optionsschaltfläche den Wert „1“, während die deaktivierte Schaltfläche den Wert „0“ hat. Der Standardwert ist eine leere Zeichenfolge. |

### Beispiele

Zeigt, wie die Eigenschaften eines ActiveX-Steuerelements überprüft werden.

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

### Siehe auch

* class [OleControl](../olecontrol/)
* namensraum [Aspose.Words.Drawing.Ole](../../aspose.words.drawing.ole/)
* Montage [Aspose.Words](../../)


