---
title: ParagraphFormat.SpaceBeforeAuto
second_title: Справочник по API Aspose.Words для .NET
description: ParagraphFormat свойство. Истинно если интервал перед абзацем устанавливается автоматически.
type: docs
weight: 320
url: /ru/net/aspose.words/paragraphformat/spacebeforeauto/
---
## ParagraphFormat.SpaceBeforeAuto property

Истинно, если интервал перед абзацем устанавливается автоматически.

```csharp
public bool SpaceBeforeAuto { get; set; }
```

### Примечания

Если установлено значение true, переопределяет эффект[`SpaceBefore`](../spacebefore/).

Когда для абзаца «Отступ до» и «Отступ после» задано значение «Авто», Microsoft Word автоматически добавляет интервал в 14 пунктов между абзацами в соответствии со следующими правилами:

* Обычно интервал добавляется после всех абзацев.
* В маркированном или нумерованном списке интервал добавляется только после последнего элемента списка. Интервал не добавляется между элементами списка.
* Во вложенных маркированных или нумерованных списках интервал не добавляется.
* Пробел обычно добавляется после таблицы.
* Пробел не добавляется после таблицы, если это последний блок в ячейке таблицы.
* Интервал не добавляется после последнего абзаца в ячейке таблицы.

### Примеры

Показывает, как установить автоматический интервал между абзацами.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Применить большое количество интервалов до и после абзацев, которые создаст этот конструктор.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Установите для этих флагов значение «true», чтобы применить автоматический интервал,
// эффективное игнорирование интервала в свойствах, которые мы установили выше.
// Оставьте их как «false», чтобы применить наш пользовательский интервал между абзацами.
builder.ParagraphFormat.SpaceAfterAuto = autoSpacing;
builder.ParagraphFormat.SpaceBeforeAuto = autoSpacing;

// Вставьте два абзаца с интервалами сверху и снизу и сохраните документ.
builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingAuto.docx");
```

### Смотрите также

* class [ParagraphFormat](../)
* пространство имен [Aspose.Words](../../paragraphformat/)
* сборка [Aspose.Words](../../../)


