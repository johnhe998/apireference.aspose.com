---
title: HtmlSaveOptions.TableWidthOutputMode
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Управляет экспортом ширины таблицы строки и ячейки в HTML MHTML или EPUB. Значение по умолчаниюAll .
type: docs
weight: 460
url: /ru/net/aspose.words.saving/htmlsaveoptions/tablewidthoutputmode/
---
## HtmlSaveOptions.TableWidthOutputMode property

Управляет экспортом ширины таблицы, строки и ячейки в HTML, MHTML или EPUB. Значение по умолчанию:All .

```csharp
public HtmlElementSizeOutputMode TableWidthOutputMode { get; set; }
```

### Примечания

В формате HTML элементы таблицы, строки и ячейки ( **&lt;таблица&gt;** , **&lt;tr&gt;** , **&lt;й&gt;** , **&lt;тд&gt;**) ширина может быть указана либо в относительных (в процентах), либо в абсолютных единицах. В документе в Aspose.Words ширина таблиц, строк и ячеек может быть указана с использованием как относительных, так и абсолютных единиц.

Когда вы конвертируете документ в HTML с помощью Aspose.Words, вы можете захотеть контролировать, как таблица, ширина строки и ячейки экспортируются, чтобы влиять на то, как результирующий документ отображается в визуальном агенте (например, браузере или средстве просмотра).

Используйте это свойство в качестве фильтра, чтобы указать, какие значения ширины таблицы экспортируются в целевой документ. Например, если вы конвертируете документ в EPUB и собираетесь просматривать документ на мобильном экспорт абсолютных значений ширины. Для этого нужно указать режим выводаRelativeOnly или жеNone , чтобы зритель на мобильном устройстве мог расположить таблицу так, чтобы она максимально соответствовала ширине экрана.

### Примеры

Показывает, как сохранить отрицательные отступы в выходном .html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставить таблицу с отрицательным отступом, который сдвинет ее влево за левую границу страницы.
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, Cell 1");
builder.InsertCell();
builder.Write("Row 1, Cell 2");
builder.EndTable();
table.LeftIndent = -36;
table.PreferredWidth = PreferredWidth.FromPoints(144);

builder.InsertBreak(BreakType.ParagraphBreak);

// Вставить таблицу с положительным отступом, который сдвинет таблицу вправо.
table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, Cell 1");
builder.InsertCell();
builder.Write("Row 1, Cell 2");
builder.EndTable();
table.LeftIndent = 36;
table.PreferredWidth = PreferredWidth.FromPoints(144);

// Когда мы сохраняем документ в HTML, Aspose.Words сохранит только отрицательные отступы
// такой же, как тот, который мы применили к первой таблице, если мы установили флаг "AllowNegativeIndent"
// в объекте SaveOptions, которому мы передадим значение «true».
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    AllowNegativeIndent = allowNegativeIndent,
    TableWidthOutputMode = HtmlElementSizeOutputMode.RelativeOnly
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.NegativeIndent.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.NegativeIndent.html");

if (allowNegativeIndent)
{
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"margin-left:-41.65pt; border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"margin-left:30.35pt; border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"margin-left:30.35pt; border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
}
```

### Смотрите также

* enum [HtmlElementSizeOutputMode](../../htmlelementsizeoutputmode/)
* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


