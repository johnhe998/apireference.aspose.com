---
title: ParagraphFormat.Bidi
second_title: Справочник по API Aspose.Words для .NET
description: ParagraphFormat свойство. Получает или задает является ли это абзацем с письмом справа налево.
type: docs
weight: 40
url: /ru/net/aspose.words/paragraphformat/bidi/
---
## ParagraphFormat.Bidi property

Получает или задает, является ли это абзацем с письмом справа налево.

```csharp
public bool Bidi { get; set; }
```

### Примечания

При значении true прогоны и другие встроенные объекты в этом параграфе располагаются справа налево.

### Примеры

Показывает, как определить направление текста в текстовом документе.

```csharp
// Создаем объект "TxtLoadOptions", который мы можем передать конструктору документа
// чтобы изменить способ загрузки документа с открытым текстом.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Установите для свойства "DocumentDirection" значение "DocumentDirection.Auto", чтобы автоматически обнаруживать
// направление каждого абзаца текста, который Aspose.Words загружает из открытого текста.
// Свойство "Bidi" каждого абзаца будет хранить его направление.
loadOptions.DocumentDirection = DocumentDirection.Auto;

// Определить текст на иврите как написанный справа налево.
Document doc = new Document(MyDir + "Hebrew text.txt", loadOptions);

Assert.True(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);

// Определить английский текст как написанный справа налево.
doc = new Document(MyDir + "English text.txt", loadOptions);

Assert.False(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);
```

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

### Смотрите также

* class [ParagraphFormat](../)
* пространство имен [Aspose.Words](../../paragraphformat/)
* сборка [Aspose.Words](../../../)


