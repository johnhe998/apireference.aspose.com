---
title: FieldShape.Text
second_title: Справочник по API Aspose.Words для .NET
description: FieldShape свойство. Получает или задает текст для извлечения.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldshape/text/
---
## FieldShape.Text property

Получает или задает текст для извлечения.

```csharp
public string Text { get; set; }
```

### Примеры

Показывает, как создавать совместимые с языком списки с написанием справа налево с полями BIDIOUTLINE.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Поле BIDIOUTLINE нумерует абзацы, как поля AUTONUM/LISTNUM,
// но отображается только при включенном языке редактирования справа налево, таком как иврит или арабский.
// Следующее поле будет отображать ".1", RTL-эквивалент номера списка "1.".
FieldBidiOutline field = (FieldBidiOutline)builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

Assert.AreEqual(" BIDIOUTLINE ", field.GetFieldCode());

// Добавьте еще два поля BIDIOUTLINE, которые будут отображать ".2" и ".3".
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

// Установить горизонтальное выравнивание текста для каждого абзаца в документе на RTL.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.Bidi = true;
}

// Если мы включим язык редактирования справа налево в Microsoft Word, наши поля будут отображать числа.
// В противном случае они будут отображать "###".
doc.Save(ArtifactsDir + "Field.BIDIOUTLINE.docx");
```

Показывает, как некоторые старые поля Microsoft Word, такие как SHAPE и EMBED, обрабатываются во время загрузки.

```csharp
// Откройте документ, созданный в Microsoft Word 2003.
Document doc = new Document(MyDir + "Legacy fields.doc");

// Если мы откроем документ Word и нажмем Alt+F9, мы увидим ФОРМУ и поле ВСТАВИТЬ.
// Поле SHAPE является якорем/холстом для объекта AutoShape с включенным стилем обтекания "В соответствии с текстом".
// Поле EMBED имеет ту же функцию, но для встроенного объекта
// например, электронная таблица из внешнего документа Excel.
// Однако эти поля не будут отображаться в коллекции Fields документа.
Assert.AreEqual(0, doc.Range.Fields.Count);

// Эти поля поддерживаются только старыми версиями Microsoft Word.
// Процесс загрузки документа преобразует эти поля в объекты Shape,
// к которому мы можем получить доступ в коллекции узлов документа.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);
Assert.AreEqual(3, shapes.Count);

// Первый узел Shape соответствует полю SHAPE во входном документе,
// который является встроенным холстом для автофигуры.
Shape shape = (Shape)shapes[0];
Assert.AreEqual(ShapeType.Image, shape.ShapeType);

// Второй узел Shape — это сама AutoShape.
shape = (Shape)shapes[1];
Assert.AreEqual(ShapeType.Can, shape.ShapeType);

// Третья форма — это то, что было полем EMBED, содержащим внешнюю электронную таблицу.
shape = (Shape)shapes[2];
Assert.AreEqual(ShapeType.OleObject, shape.ShapeType);
```

### Смотрите также

* class [FieldShape](../)
* пространство имен [Aspose.Words.Fields](../../fieldshape/)
* сборка [Aspose.Words](../../../)


