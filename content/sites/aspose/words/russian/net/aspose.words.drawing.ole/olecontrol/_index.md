---
title: Class OleControl
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.Ole.OleControl сорт. Представляет элемент управления OLE ActiveX.
type: docs
weight: 1010
url: /ru/net/aspose.words.drawing.ole/olecontrol/
---
## OleControl class

Представляет элемент управления OLE ActiveX.

```csharp
public class OleControl
```

## Характеристики

| Имя | Описание |
| --- | --- |
| virtual [IsForms2OleControl](../../aspose.words.drawing.ole/olecontrol/isforms2olecontrol/) { get; } | Возвращает true, если элемент управления является[`Forms2OleControl`](../forms2olecontrol/) . |
| [Name](../../aspose.words.drawing.ole/olecontrol/name/) { get; } | Получает имя элемента управления ActiveX. |

### Примеры

Показывает, как проверить свойства элемента управления ActiveX.

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

### Смотрите также

* пространство имен [Aspose.Words.Drawing.Ole](../../aspose.words.drawing.ole/)
* сборка [Aspose.Words](../../)


