---
title: NodeRendererBase.Save
second_title: Справочник по API Aspose.Words для .NET
description: NodeRendererBase метод. Преобразует фигуру в изображение и сохраняет в файл.
type: docs
weight: 90
url: /ru/net/aspose.words.rendering/noderendererbase/save/
---
## Save(string, ImageSaveOptions) {#save_1}

Преобразует фигуру в изображение и сохраняет в файл.

```csharp
public void Save(string fileName, ImageSaveOptions saveOptions)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| fileName | String | Имя файла изображения. Если файл с указанным именем уже существует, существующий файл перезаписывается. |
| saveOptions | ImageSaveOptions | Указывает параметры, управляющие визуализацией и сохранением фигуры. Может быть нулевым. |

### Примеры

Показывает, как преобразовать объект Office Math в файл изображения в локальной файловой системе.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// Создаем объект "ImageSaveOptions" для передачи в метод "Сохранить" средства визуализации узла для изменения
// как он отображает узел OfficeMath в изображение.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// Установите для свойства «Масштаб» значение 5, чтобы отобразить объект в пять раз больше его исходного размера.
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

### Смотрите также

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* пространство имен [Aspose.Words.Rendering](../../noderendererbase/)
* сборка [Aspose.Words](../../../)

---

## Save(Stream, ImageSaveOptions) {#save}

Преобразует форму в изображение и сохраняет в поток.

```csharp
public void Save(Stream stream, ImageSaveOptions saveOptions)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| stream | Stream | Поток, в котором нужно сохранить изображение фигуры. |
| saveOptions | ImageSaveOptions | Указывает параметры, управляющие визуализацией и сохранением фигуры. Может быть null. Если это значение null, изображение будет сохранено в формате PNG. |

### Примеры

Показывает, как использовать средство визуализации фигур для экспорта фигур в файлы в локальной файловой системе.

```csharp
Document doc = new Document(MyDir + "Various shapes.docx");
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(7, shapes.Length);

// В документе 7 фигур, в том числе одна групповая фигура с 2 дочерними фигурами.
// Мы будем отображать каждую фигуру в файл изображения в локальной файловой системе
// при игнорировании групповых форм, поскольку они не имеют внешнего вида.
// Это создаст 6 файлов изображений.
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>())
{
    ShapeRenderer renderer = shape.GetShapeRenderer();
    ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
    renderer.Save(ArtifactsDir + $"Shape.RenderAllShapes.{shape.Name}.png", options);
}
```

### Смотрите также

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* пространство имен [Aspose.Words.Rendering](../../noderendererbase/)
* сборка [Aspose.Words](../../../)


