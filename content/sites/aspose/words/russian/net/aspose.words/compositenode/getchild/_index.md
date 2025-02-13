---
title: CompositeNode.GetChild
second_title: Справочник по API Aspose.Words для .NET
description: CompositeNode метод. Возвращает Nй дочерний узел соответствующий указанному типу.
type: docs
weight: 90
url: /ru/net/aspose.words/compositenode/getchild/
---
## CompositeNode.GetChild method

Возвращает N-й дочерний узел, соответствующий указанному типу.

```csharp
public Node GetChild(NodeType nodeType, int index, bool isDeep)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| nodeType | NodeType | Указывает тип дочернего узла. |
| index | Int32 | Отсчитываемый от нуля индекс дочернего узла для выбора. Отрицательные индексы также разрешены и указывают на доступ с конца, , то есть -1 означает последний узел. |
| isDeep | Boolean | True для рекурсивного выбора из всех дочерних узлов. False для выбора только среди непосредственных дочерних узлов. См. комментарии для получения дополнительной информации. |

### Возвращаемое значение

Дочерний узел, соответствующий критериям, или null, если соответствующий узел не найден.

### Примечания

Если индекс выходит за пределы допустимого диапазона, возвращается нуль.

Обратите внимание, что узлы разметки (StructuredDocumentTag а такжеSmartTag) просматриваются, даже если isDeep = false и GetChild вызывается для типа узла без разметки. Например, если первый запуск в параграфе заключен в StructuredDocumentTag, он все равно будет возвращен GetChild(NodeType.Run, 0, false).

### Примеры

Показывает, как применить свойства стиля таблицы непосредственно к элементам таблицы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Hello world!");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.RowStripe = 3;
tableStyle.CellSpacing = 5;
tableStyle.Shading.BackgroundPatternColor = Color.AntiqueWhite;
tableStyle.Borders.Color = Color.Blue;
tableStyle.Borders.LineStyle = LineStyle.DotDash;

table.Style = tableStyle;

// Этот метод относится к свойствам стиля таблицы, таким как те, которые мы установили выше.
doc.ExpandTableStylesToDirectFormatting();

doc.Save(ArtifactsDir + "Document.TableStyleToDirectFormatting.docx");
```

Показывает, как пройти через коллекцию дочерних узлов составного узла.

```csharp
Document doc = new Document();

// Добавьте два прогона и одну фигуру в качестве дочерних узлов в первый абзац этого документа.
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
paragraph.AppendChild(new Run(doc, "Hello world! "));

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
// Обратите внимание, что 'CustomNodeId' не сохраняется в выходной файл и существует только во время жизни узла.
shape.CustomNodeId = 100;
shape.WrapType = WrapType.Inline;
paragraph.AppendChild(shape);

paragraph.AppendChild(new Run(doc, "Hello again!"));

// Итерация по коллекции непосредственных дочерних элементов абзаца,
// и печатаем любые прогоны или формы, которые мы находим внутри.
NodeCollection children = paragraph.ChildNodes;

Assert.AreEqual(3, paragraph.ChildNodes.Count);

foreach (Node child in children)
    switch (child.NodeType)
    {
        case NodeType.Run:
            Console.WriteLine("Run contents:");
            Console.WriteLine($"\t\"{child.GetText().Trim()}\"");
            break;
        case NodeType.Shape:
            Shape childShape = (Shape)child;
            Console.WriteLine("Shape:");
            Console.WriteLine($"\t{childShape.ShapeType}, {childShape.Width}x{childShape.Height}");
    }
```

### Смотрите также

* class [Node](../../node/)
* enum [NodeType](../../nodetype/)
* class [CompositeNode](../)
* пространство имен [Aspose.Words](../../compositenode/)
* сборка [Aspose.Words](../../../)


