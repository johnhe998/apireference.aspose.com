---
title: LayoutCollector.Document
second_title: Справочник по API Aspose.Words для .NET
description: LayoutCollector свойство. Получает или задает документ к которому прикреплен этот экземпляр сборщика.
type: docs
weight: 20
url: /ru/net/aspose.words.layout/layoutcollector/document/
---
## LayoutCollector.Document property

Получает или задает документ, к которому прикреплен этот экземпляр сборщика.

```csharp
public Document Document { get; set; }
```

### Примечания

Если вам нужно получить доступ к индексам страниц узлов документа, вам нужно установить это свойство так, чтобы оно указывало на экземпляр документа, до того, как будет создан макет страницы документа. Лучше всего установить это свойство в`нулевой`после этого в противном случае сборщик продолжает накапливать информацию из последующих перестроек макета страницы документа.

### Примеры

Показывает, как просмотреть диапазоны страниц, которые охватывает узел.

```csharp
Document doc = new Document();
LayoutCollector layoutCollector = new LayoutCollector(doc);

// Вызовите метод «GetNumPagesSpanned», чтобы подсчитать, сколько страниц занимает содержимое нашего документа.
// Поскольку документ пуст, это количество страниц в настоящее время равно нулю.
Assert.AreEqual(doc, layoutCollector.Document);
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

// Заполнить документ 5 страницами содержимого.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Section 1");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);

// Перед сборщиком макетов нам нужно вызвать метод «UpdatePageLayout», чтобы получить
// точная цифра для любой метрики, связанной с макетом, например, для количества страниц.
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

layoutCollector.Clear();
doc.UpdatePageLayout();

Assert.AreEqual(5, layoutCollector.GetNumPagesSpanned(doc));

// Мы можем видеть номера начальной и конечной страниц любого узла и их общий диапазон страниц.
NodeCollection nodes = doc.GetChildNodes(NodeType.Any, true);
foreach (Node node in nodes)
{
    Console.WriteLine($"->  NodeType.{node.NodeType}: ");
    Console.WriteLine(
        $"\tStarts on page {layoutCollector.GetStartPageIndex(node)}, ends on page {layoutCollector.GetEndPageIndex(node)}," +
        $" spanning {layoutCollector.GetNumPagesSpanned(node)} pages.");
}

// Мы можем перебирать объекты макета с помощью LayoutEnumerator.
LayoutEnumerator layoutEnumerator = new LayoutEnumerator(doc);

Assert.AreEqual(LayoutEntityType.Page, layoutEnumerator.Type);

// LayoutEnumerator может перемещаться по коллекции сущностей макета, как по дереву.
// Мы также можем применить его к соответствующему объекту макета любого узла.
layoutEnumerator.Current = layoutCollector.GetEntity(doc.GetChild(NodeType.Paragraph, 1, true));

Assert.AreEqual(LayoutEntityType.Span, layoutEnumerator.Type);
Assert.AreEqual("¶", layoutEnumerator.Text);
```

### Смотрите также

* class [Document](../../../aspose.words/document/)
* class [LayoutCollector](../)
* пространство имен [Aspose.Words.Layout](../../layoutcollector/)
* сборка [Aspose.Words](../../../)


