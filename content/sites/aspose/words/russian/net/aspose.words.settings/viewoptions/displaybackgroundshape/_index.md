---
title: ViewOptions.DisplayBackgroundShape
second_title: Справочник по API Aspose.Words для .NET
description: ViewOptions свойство. Управляет отображением формы фона в макете печати.
type: docs
weight: 10
url: /ru/net/aspose.words.settings/viewoptions/displaybackgroundshape/
---
## ViewOptions.DisplayBackgroundShape property

Управляет отображением формы фона в макете печати.

```csharp
public bool DisplayBackgroundShape { get; set; }
```

### Примеры

Показывает, как скрыть/отобразить фоновые изображения документа в параметрах просмотра.

```csharp
// Используйте строку HTML для создания нового документа с однотонным фоном.
const string html = 
@"<html>
    <body style='background-color: blue'>
        <p>Hello world!</p>
    </body>
</html>";

Document doc = new Document(new MemoryStream(Encoding.Unicode.GetBytes(html)));

// Исходник документа имеет плоский цвет фона,
// наличие которого установит флаг "DisplayBackgroundShape" в "true".
Assert.True(doc.ViewOptions.DisplayBackgroundShape);

// Оставьте «DisplayBackgroundShape» равным «true», чтобы документ отображал цвет фона.
// Это может повлиять на некоторые цвета текста для улучшения видимости.
// Установите «DisplayBackgroundShape» в «false», чтобы не отображать цвет фона.
doc.ViewOptions.DisplayBackgroundShape = displayBackgroundShape;

doc.Save(ArtifactsDir + "ViewOptions.DisplayBackgroundShape.docx");
```

### Смотрите также

* class [ViewOptions](../)
* пространство имен [Aspose.Words.Settings](../../viewoptions/)
* сборка [Aspose.Words](../../../)


