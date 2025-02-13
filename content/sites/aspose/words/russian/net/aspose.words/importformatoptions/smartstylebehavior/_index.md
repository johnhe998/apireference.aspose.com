---
title: ImportFormatOptions.SmartStyleBehavior
second_title: Справочник по API Aspose.Words для .NET
description: ImportFormatOptions свойство. Получает или задает логическое значение указывающее как будут импортироваться стили  если они имеют одинаковые имена в исходном и целевом документах. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 70
url: /ru/net/aspose.words/importformatoptions/smartstylebehavior/
---
## ImportFormatOptions.SmartStyleBehavior property

Получает или задает логическое значение, указывающее, как будут импортироваться стили , если они имеют одинаковые имена в исходном и целевом документах. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool SmartStyleBehavior { get; set; }
```

### Примечания

Когда этот вариант **включено** , исходный стиль будет развернут в прямые атрибуты внутри целевого документа a , еслиKeepSourceFormatting используется режим импорта.

Когда этот вариант **инвалид**, исходный стиль будет развернут, только если он пронумерован. Существующие атрибуты назначения не будут переопределены, включая списки.

### Примеры

Показывает, как разрешать повторяющиеся стили при вставке документов.

```csharp
Document dstDoc = new Document();
DocumentBuilder builder = new DocumentBuilder(dstDoc);

Style myStyle = builder.Document.Styles.Add(StyleType.Paragraph, "MyStyle");
myStyle.Font.Size = 14;
myStyle.Font.Name = "Courier New";
myStyle.Font.Color = Color.Blue;

builder.ParagraphFormat.StyleName = myStyle.Name;
builder.Writeln("Hello world!");

// Клонируем документ и редактируем стиль "MyStyle" клона, чтобы он отличался от цвета оригинала.
// Если мы вставим клон в исходный документ, два стиля с одинаковыми именами вызовут конфликт.
Document srcDoc = dstDoc.Clone();
srcDoc.Styles["MyStyle"].Font.Color = Color.Red;

// Когда мы включаем SmartStyleBehavior и используем режим формата импорта KeepSourceFormatting,
// Aspose.Words разрешает конфликты стилей путем преобразования стилей исходного документа.
// с теми же именами, что и целевые стили, в прямые атрибуты абзаца.
ImportFormatOptions options = new ImportFormatOptions();
options.SmartStyleBehavior = true;

builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);

dstDoc.Save(ArtifactsDir + "DocumentBuilder.SmartStyleBehavior.docx");
```

### Смотрите также

* class [ImportFormatOptions](../)
* пространство имен [Aspose.Words](../../importformatoptions/)
* сборка [Aspose.Words](../../../)


