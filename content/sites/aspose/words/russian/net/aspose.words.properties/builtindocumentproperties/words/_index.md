---
title: BuiltInDocumentProperties.Words
second_title: Справочник по API Aspose.Words для .NET
description: BuiltInDocumentProperties свойство. Представляет оценку количества слов в документе.
type: docs
weight: 330
url: /ru/net/aspose.words.properties/builtindocumentproperties/words/
---
## BuiltInDocumentProperties.Words property

Представляет оценку количества слов в документе.

```csharp
public int Words { get; set; }
```

### Примечания

Aspose.Words обновляет это свойство при вызове[`UpdateWordCount`](../../../aspose.words/document/updatewordcount/).

### Примеры

Показывает, как обновить все метки списков в документе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
builder.Write("Ut enim ad minim veniam, " +
                "quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

// Aspose.Words не отслеживает подобные показатели документов в режиме реального времени.
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Paragraphs);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

// Чтобы получить точные значения для трех из этих свойств, нам нужно будет обновить их вручную.
doc.UpdateWordCount();

Assert.AreEqual(196, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(36, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(2, doc.BuiltInDocumentProperties.Paragraphs);

// Для подсчета строк нам потребуется вызвать специальную перегрузку метода обновления.
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

doc.UpdateWordCount(true);

Assert.AreEqual(4, doc.BuiltInDocumentProperties.Lines);
```

Показывает, как работать со свойствами документа в категории «Содержание».

```csharp
public void Content()
{
    Document doc = new Document(MyDir + "Paragraphs.docx");
    BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

    // Используя встроенные свойства,
    // мы можем рассматривать статистику документа, такую как количество слов/страниц/символов, как метаданные, которые можно просмотреть, не открывая документ
    // Доступ к этим свойствам можно получить, щелкнув файл правой кнопкой мыши в проводнике Windows и выбрав Свойства > Подробности > Содержание
    // Если мы хотим отобразить эти данные внутри документа, мы можем использовать такие поля, как NUMPAGES, NUMWORDS, NUMCHARS и т. д.
    // Кроме того, эти значения также можно просмотреть в Microsoft Word, выбрав Файл > Свойства > Дополнительные свойства > Статистика
    // Количество страниц: свойство PageCount показывает количество страниц в реальном времени, и его значение может быть присвоено свойству Pages

    // Свойство "Страницы" хранит количество страниц документа. 
    Assert.AreEqual(6, properties.Pages);

    // Встроенные свойства "Words", "Characters" и "CharactersWithSpaces" также отображают различную статистику документа,
    // но нам нужно вызвать метод "UpdateWordCount" для всего документа, прежде чем мы сможем ожидать, что они будут содержать точные значения.
    doc.UpdateWordCount();

    Assert.AreEqual(1035, properties.Words);
    Assert.AreEqual(6026, properties.Characters);
    Assert.AreEqual(7041, properties.CharactersWithSpaces);

    // Подсчитаем количество строк в документе, а затем присвоим результат встроенному свойству «Строки».
    LineCounter lineCounter = new LineCounter(doc);
    properties.Lines = lineCounter.GetLineCount();

    Assert.AreEqual(142, properties.Lines);

    // Назначаем количество узлов абзаца в документе встроенному свойству «Абзацы».
    properties.Paragraphs = doc.GetChildNodes(NodeType.Paragraph, true).Count;
    Assert.AreEqual(29, properties.Paragraphs);

    // Получить оценку размера файла нашего документа с помощью встроенного свойства «Bytes».
    Assert.AreEqual(20310, properties.Bytes);

    // Установите другой шаблон для нашего документа, а затем обновите встроенное свойство «Шаблон» вручную, чтобы отразить это изменение.
    doc.AttachedTemplate = MyDir + "Business brochure.dotx";

    Assert.AreEqual("Normal", properties.Template);    

    properties.Template = doc.AttachedTemplate;

    // «ContentStatus» — описательное встроенное свойство.
    properties.ContentStatus = "Draft";

    // При сохранении встроенное свойство ContentType будет содержать MIME-тип выходного формата сохранения.
    Assert.AreEqual(string.Empty, properties.ContentType);

    // Если документ содержит ссылки и все они актуальны, мы можем установить для свойства LinksUpToDate значение true.
    Assert.False(properties.LinksUpToDate);

    doc.Save(ArtifactsDir + "DocumentProperties.Content.docx");
}

/// <summary>
/// Подсчитывает строки в документе.
/// Просматривает дерево сущностей макета документа при построении,
/// подсчет объектов типа "Линия", которые также содержат реальный текст.
/// </summary>
private class LineCounter
{
    public LineCounter(Document doc)
    {
        mLayoutEnumerator = new LayoutEnumerator(doc);

        CountLines();
    }

    public int GetLineCount()
    {
        return mLineCount;
    }

    private void CountLines()
    {
        do
        {
            if (mLayoutEnumerator.Type == LayoutEntityType.Line)
            {
                mScanningLineForRealText = true;
            }

            if (mLayoutEnumerator.MoveFirstChild())
            {
                if (mScanningLineForRealText && mLayoutEnumerator.Kind.StartsWith("TEXT"))
                {
                    mLineCount++;
                    mScanningLineForRealText = false;
                }
                CountLines();
                mLayoutEnumerator.MoveParent();
            }
        } while (mLayoutEnumerator.MoveNext());
    }

    private readonly LayoutEnumerator mLayoutEnumerator;
    private int mLineCount;
    private bool mScanningLineForRealText;
}
```

### Смотрите также

* class [BuiltInDocumentProperties](../)
* пространство имен [Aspose.Words.Properties](../../builtindocumentproperties/)
* сборка [Aspose.Words](../../../)


