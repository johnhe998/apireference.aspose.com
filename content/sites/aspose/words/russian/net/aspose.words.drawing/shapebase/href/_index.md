---
title: ShapeBase.HRef
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Получает или задает полный адрес гиперссылки для фигуры.
type: docs
weight: 220
url: /ru/net/aspose.words.drawing/shapebase/href/
---
## ShapeBase.HRef property

Получает или задает полный адрес гиперссылки для фигуры.

```csharp
public string HRef { get; set; }
```

### Примечания

Значение по умолчанию — пустая строка.

Ниже приведены примеры допустимых значений этого свойства:

Полный URI:`https://www.aspose.com/`.

Полное имя файла:`C:\\Мои документы\\SalesReport.doc`.

Относительный URI:`../../../resource.txt`

Относительное имя файла:`..\\Мои документы\\SalesReport.doc`.

Закладка в другом документе:`https://www.aspose.com/Products/Default.aspx#Suites`

Закладка в этом документе:`#BookmakName`.

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


