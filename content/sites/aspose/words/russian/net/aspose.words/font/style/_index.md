---
title: Font.Style
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Получает или задает стиль символов применяемый к этому форматированию.
type: docs
weight: 400
url: /ru/net/aspose.words/font/style/
---
## Font.Style property

Получает или задает стиль символов, применяемый к этому форматированию.

```csharp
public Style Style { get; set; }
```

### Примеры

Применяет двойное подчеркивание ко всем прогонам в документе, отформатированным с использованием пользовательских стилей символов.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте пользовательский стиль и примените его к тексту, созданному с помощью конструктора документов.
Style style = doc.Styles.Add(StyleType.Character, "MyStyle");
style.Font.Color = Color.Red;
style.Font.Name = "Courier New";

builder.Font.StyleName = "MyStyle";
builder.Write("This text is in a custom style.");

// Повторяем каждый запуск и добавляем двойное подчеркивание к каждому пользовательскому стилю.
foreach (Run run in doc.GetChildNodes(NodeType.Run, true).OfType<Run>())
{
    Style charStyle = run.Font.Style;

    if (!charStyle.BuiltIn)
        run.Font.Underline = Underline.Double;
}

doc.Save(ArtifactsDir + "Font.Style.docx");
```

### Смотрите также

* class [Style](../../style/)
* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


