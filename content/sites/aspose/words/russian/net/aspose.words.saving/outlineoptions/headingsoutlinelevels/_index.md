---
title: OutlineOptions.HeadingsOutlineLevels
second_title: Справочник по API Aspose.Words для .NET
description: OutlineOptions свойство. Указывает сколько уровней заголовков абзацев отформатированных с помощью стилей заголовков включить в структуру документа .
type: docs
weight: 70
url: /ru/net/aspose.words.saving/outlineoptions/headingsoutlinelevels/
---
## OutlineOptions.HeadingsOutlineLevels property

Указывает, сколько уровней заголовков (абзацев, отформатированных с помощью стилей заголовков) включить в структуру документа .

```csharp
public int HeadingsOutlineLevels { get; set; }
```

### Примечания

Укажите 0, чтобы в структуре не было заголовков; указать 1 для одного уровня заголовков в структуре и т.д.

Значение по умолчанию — 0. Допустимый диапазон — от 0 до 9.

### Примеры

Показывает, как преобразовать весь документ в PDF с тремя уровнями структуры документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставляем заголовки уровней с 1 по 5.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;

builder.Writeln("Heading 1.2.2.1");
builder.Writeln("Heading 1.2.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.2.2.2.1");
builder.Writeln("Heading 1.2.2.2.2");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Выходной PDF-документ будет содержать структуру, которая представляет собой оглавление, в котором перечислены заголовки в теле документа.
// Нажав на запись в этой схеме, мы перейдем к расположению соответствующего заголовка.
// Установите для свойства "HeadingsOutlineLevels" значение "4", чтобы исключить из структуры все заголовки, уровни которых выше 4.
options.OutlineOptions.HeadingsOutlineLevels = 4;

// Если запись схемы имеет последующие записи более высокого уровня между собой и следующей записью того же или более низкого уровня,
// слева от записи появится стрелка. Эта запись является «владельцем» нескольких таких «подзаписей».
// В нашем документе элементы структуры с 5-го уровня заголовка являются подстатьями второго элемента структуры 4-го уровня,
 // статьи 4-го и 5-го уровня заголовков являются подстатьями второй записи 3-го уровня и т.д.
// В схеме мы можем щелкнуть стрелку записи «владелец», чтобы свернуть/развернуть все ее подзаписи.
// Установите для свойства «ExpandedOutlineLevels» значение «2», чтобы автоматически расширять все элементы уровня заголовка 2 и нижнего уровня структуры
 // и свернуть все записи уровня и 3 и выше при открытии документа.
options.OutlineOptions.ExpandedOutlineLevels = 2;

doc.Save(ArtifactsDir + "PdfSaveOptions.ExpandedOutlineLevels.pdf", options);
```

### Смотрите также

* class [OutlineOptions](../)
* пространство имен [Aspose.Words.Saving](../../outlineoptions/)
* сборка [Aspose.Words](../../../)


