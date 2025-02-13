---
title: ShapeBase.Target
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Получает или задает целевой кадр для гиперссылки формы.
type: docs
weight: 480
url: /ru/net/aspose.words.drawing/shapebase/target/
---
## ShapeBase.Target property

Получает или задает целевой кадр для гиперссылки формы.

```csharp
public string Target { get; set; }
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


