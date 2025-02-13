---
title: Enum ParagraphAlignment
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.ParagraphAlignment перечисление. Задает выравнивание текста в абзаце.
type: docs
weight: 4160
url: /ru/net/aspose.words/paragraphalignment/
---
## ParagraphAlignment enumeration

Задает выравнивание текста в абзаце.

```csharp
public enum ParagraphAlignment
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Left | `0` | Текст выровнен по левому краю. |
| Center | `1` | Текст центрирован по горизонтали. |
| Right | `2` | Текст выровнен по правому краю. |
| Justify | `3` | Текст выровнен по левому и правому краю. |
| Distributed | `4` | Текст распределен равномерно. |
| ArabicMediumKashida | `5` | Только арабский. Длина кашиды для текста увеличена до средней длины, определяемой потребителем. |
| ArabicHighKashida | `7` | Только арабский. Длина кашиды для текста увеличена до максимально возможной длины. |
| ArabicLowKashida | `8` | Только арабский. Длина кашиды для текста увеличена до немного большей длины. |
| ThaiDistributed | `9` | Только тайский. Текст выровнен с оптимизацией для тайского языка. |
| MathElementCenterAsGroup | `10` | Единственный математический элемент в строке, выровненный как «По центру группы». |

### Примеры

Показывает, как создать документ Aspose.Words вручную.

```csharp
Document doc = new Document();

// Пустой документ содержит один раздел, одно тело и один абзац.
// Вызовите метод "RemoveAllChildren", чтобы удалить все эти узлы,
// и получаем узел документа без дочерних элементов.
doc.RemoveAllChildren();

// Этот документ теперь не имеет составных дочерних узлов, к которым мы можем добавить содержимое.
// Если мы хотим отредактировать его, нам нужно будет повторно заполнить его коллекцию узлов.
// Сначала создайте новый раздел, а затем добавьте его как дочерний к корневому узлу документа.
Section section = new Section(doc);
doc.AppendChild(section);

// Установите некоторые свойства настройки страницы для раздела.
section.PageSetup.SectionStart = SectionStart.NewPage;
section.PageSetup.PaperSize = PaperSize.Letter;

// Разделу нужно тело, которое будет содержать и отображать все его содержимое
// на странице между шапкой и нижним колонтитулом раздела.
Body body = new Body(doc);
section.AppendChild(body);

// Создать абзац, установить некоторые свойства форматирования, а затем добавить его в тело как дочерний элемент.
Paragraph para = new Paragraph(doc);

para.ParagraphFormat.StyleName = "Heading 1";
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;

body.AppendChild(para);

// Наконец, добавьте содержимое для создания документа. Создать прогон,
// установить его внешний вид и содержимое, а затем добавить его как дочерний элемент к абзацу.
Run run = new Run(doc);
run.Text = "Hello World!";
run.Font.Color = Color.Red;
para.AppendChild(run);

Assert.AreEqual("Hello World!", doc.GetText().Trim());

doc.Save(ArtifactsDir + "Section.CreateManually.docx");
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


