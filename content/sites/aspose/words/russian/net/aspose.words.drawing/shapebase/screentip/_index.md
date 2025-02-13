---
title: ShapeBase.ScreenTip
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Определяет текст отображаемый при наведении указателя мыши на фигуру.
type: docs
weight: 440
url: /ru/net/aspose.words.drawing/shapebase/screentip/
---
## ShapeBase.ScreenTip property

Определяет текст, отображаемый при наведении указателя мыши на фигуру.

```csharp
public string ScreenTip { get; set; }
```

### Примечания

Значение по умолчанию — пустая строка.

### Примеры

Показывает, как вставить фигуру, которая содержит изображение и также является гиперссылкой.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.HRef = "https://форум.aspose.com/";
shape.Target = "New Window";
shape.ScreenTip = "Aspose.Words Support Forums";

// Ctrl + щелчок левой кнопкой мыши по фигуре в Microsoft Word откроет новое окно веб-браузера
// и переходим к гиперссылке в свойстве "HRef".
doc.Save(ArtifactsDir + "Image.InsertImageWithHyperlink.docx");
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


