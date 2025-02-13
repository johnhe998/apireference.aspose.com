---
title: OfficeMath.Justification
second_title: Справочник по API Aspose.Words для .NET
description: OfficeMath свойство. Получает/устанавливает выравнивание Office Math.
type: docs
weight: 30
url: /ru/net/aspose.words.math/officemath/justification/
---
## OfficeMath.Justification property

Получает/устанавливает выравнивание Office Math.

```csharp
public OfficeMathJustification Justification { get; set; }
```

### Примечания

Обоснование не может быть установлено на Office Math с типом формата отображенияInline.

Встроенное выравнивание не может быть установлено на Office Math с типом формата отображенияDisplay.

Соответствующий[`DisplayType`](../displaytype/) должен быть установлен перед настройкой выравнивания Office Math.

### Примеры

Показывает, как настроить формат отображения математических данных в офисе.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath) doc.GetChild(NodeType.OfficeMath, 0, true);

// Узлы OfficeMath, являющиеся потомками других узлов OfficeMath, всегда являются встроенными.
// Узел, с которым мы работаем, является базовым узлом для изменения его местоположения и типа отображения.
Assert.AreEqual(MathObjectType.OMathPara, officeMath.MathObjectType);
Assert.AreEqual(NodeType.OfficeMath, officeMath.NodeType);
Assert.AreEqual(officeMath.ParentNode, officeMath.ParentParagraph);

// Форматы OOXML и WML используют свойство "EquationXmlEncoding".
Assert.IsNull(officeMath.EquationXmlEncoding);

// Измените расположение и тип отображения узла OfficeMath.
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

doc.Save(ArtifactsDir + "Shape.OfficeMath.docx");
```

### Смотрите также

* enum [OfficeMathJustification](../../officemathjustification/)
* class [OfficeMath](../)
* пространство имен [Aspose.Words.Math](../../officemath/)
* сборка [Aspose.Words](../../../)


