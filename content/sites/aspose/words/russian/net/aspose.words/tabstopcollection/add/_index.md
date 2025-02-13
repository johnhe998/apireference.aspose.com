---
title: TabStopCollection.Add
second_title: Справочник по API Aspose.Words для .NET
description: TabStopCollection метод. Добавляет или заменяет позицию табуляции в коллекции.
type: docs
weight: 30
url: /ru/net/aspose.words/tabstopcollection/add/
---
## Add(TabStop) {#add}

Добавляет или заменяет позицию табуляции в коллекции.

```csharp
public void Add(TabStop tabStop)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| tabStop | TabStop | Объект табуляции для добавления. |

### Примечания

Если табуляция уже существует в указанной позиции, она заменяется.

### Примеры

Показывает, как добавить пользовательские позиции табуляции в документ.

```csharp
Document doc = new Document();
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// Ниже приведены два способа добавления позиций табуляции в коллекцию позиций табуляции абзаца с помощью свойства «ParagraphFormat».
// 1 - Создадим объект "TabStop", а затем добавим его в коллекцию:
TabStop tabStop = new TabStop(ConvertUtil.InchToPoint(3), TabAlignment.Left, TabLeader.Dashes);
paragraph.ParagraphFormat.TabStops.Add(tabStop);

// 2 - Передаем значения свойств новой табуляции в метод "Добавить":
paragraph.ParagraphFormat.TabStops.Add(ConvertUtil.MillimeterToPoint(100), TabAlignment.Left,
    TabLeader.Dashes);

// Добавляем позиции табуляции на расстоянии 5 см ко всем абзацам.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
{
    para.ParagraphFormat.TabStops.Add(ConvertUtil.MillimeterToPoint(50), TabAlignment.Left,
        TabLeader.Dashes);
}

// Каждый символ табуляции переводит курсор конструктора в положение следующей позиции табуляции.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Start\tTab 1\tTab 2\tTab 3\tTab 4");

doc.Save(ArtifactsDir + "TabStopCollection.AddTabStops.docx");
```

### Смотрите также

* class [TabStop](../../tabstop/)
* class [TabStopCollection](../)
* пространство имен [Aspose.Words](../../tabstopcollection/)
* сборка [Aspose.Words](../../../)

---

## Add(double, TabAlignment, TabLeader) {#add_1}

Добавляет или заменяет позицию табуляции в коллекции.

```csharp
public void Add(double position, TabAlignment alignment, TabLeader leader)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| position | Double | Позиция (в пунктах), где добавить позицию табуляции. |
| alignment | TabAlignment | А[`TabAlignment`](../../tabalignment/)значение that определяет выравнивание текста по позиции табуляции. |
| leader | TabLeader | А[`TabLeader`](../../tableader/) значение that определяет тип линии выноски, отображаемой под символом табуляции. |

### Примечания

Если табуляция уже существует в указанной позиции, она заменяется.

### Примеры

Показывает, как добавить пользовательские позиции табуляции в документ.

```csharp
Document doc = new Document();
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// Ниже приведены два способа добавления позиций табуляции в коллекцию позиций табуляции абзаца с помощью свойства «ParagraphFormat».
// 1 - Создадим объект "TabStop", а затем добавим его в коллекцию:
TabStop tabStop = new TabStop(ConvertUtil.InchToPoint(3), TabAlignment.Left, TabLeader.Dashes);
paragraph.ParagraphFormat.TabStops.Add(tabStop);

// 2 - Передаем значения свойств новой табуляции в метод "Добавить":
paragraph.ParagraphFormat.TabStops.Add(ConvertUtil.MillimeterToPoint(100), TabAlignment.Left,
    TabLeader.Dashes);

// Добавляем позиции табуляции на расстоянии 5 см ко всем абзацам.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
{
    para.ParagraphFormat.TabStops.Add(ConvertUtil.MillimeterToPoint(50), TabAlignment.Left,
        TabLeader.Dashes);
}

// Каждый символ табуляции переводит курсор конструктора в положение следующей позиции табуляции.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Start\tTab 1\tTab 2\tTab 3\tTab 4");

doc.Save(ArtifactsDir + "TabStopCollection.AddTabStops.docx");
```

### Смотрите также

* enum [TabAlignment](../../tabalignment/)
* enum [TabLeader](../../tableader/)
* class [TabStopCollection](../)
* пространство имен [Aspose.Words](../../tabstopcollection/)
* сборка [Aspose.Words](../../../)


