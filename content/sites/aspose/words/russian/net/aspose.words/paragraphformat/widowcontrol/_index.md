---
title: ParagraphFormat.WidowControl
second_title: Справочник по API Aspose.Words для .NET
description: ParagraphFormat свойство. Истинно если первая и последняя строки в абзаце должны оставаться на той же странице что и остальная часть абзаца.
type: docs
weight: 390
url: /ru/net/aspose.words/paragraphformat/widowcontrol/
---
## ParagraphFormat.WidowControl property

Истинно, если первая и последняя строки в абзаце должны оставаться на той же странице, что и остальная часть абзаца.

```csharp
public bool WidowControl { get; set; }
```

### Примеры

Показывает, как включить управление вдовой/сиротой для абзаца.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Когда мы пишем текст, который не помещается на одной странице, одна строка может перекинуться на следующую страницу.
// Единственная строка, которая заканчивается на следующей странице, называется "сиротой",
// а предыдущая строка, где обрывается сирота, называется "Вдова".
// Мы можем исправить сирот и вдов, изменив порядок текста с помощью размера шрифта, интервала или полей страницы.
// Если мы хотим сохранить размеры нашего документа, мы можем установить этот флаг в "true"
 // чтобы поместить вдовы на ту же страницу, что и их соответствующие сироты.
// Оставьте для этого флага значение "false", и в тексте останутся пары "вдова/сирота".
// Этот параметр доступен для каждого абзаца в Microsoft Word через Home -> Абзац -> Настройки абзаца
// (кнопка в правом нижнем углу вкладки "Абзац") -> «Контроль вдовы/сироты».
builder.ParagraphFormat.WidowControl = widowControl; 

// Вставляем текст, который производит сироту и вдову.
builder.Font.Size = 68;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "ParagraphFormat.WidowControl.docx");
```

### Смотрите также

* class [ParagraphFormat](../)
* пространство имен [Aspose.Words](../../paragraphformat/)
* сборка [Aspose.Words](../../../)


