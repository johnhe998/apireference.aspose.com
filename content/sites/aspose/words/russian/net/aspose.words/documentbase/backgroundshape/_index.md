---
title: DocumentBase.BackgroundShape
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBase свойство. Получает или задает форму фона документа. Может быть нулевым.
type: docs
weight: 10
url: /ru/net/aspose.words/documentbase/backgroundshape/
---
## DocumentBase.BackgroundShape property

Получает или задает форму фона документа. Может быть нулевым.

```csharp
public Shape BackgroundShape { get; set; }
```

### Примечания

Microsoft Word допускает только ту форму, которая имеет свою[`ShapeType`](../../../aspose.words.drawing/shapebase/shapetype/) свойство, равное Rectangle для использования в качестве фоновой формы для документа.

Microsoft Word поддерживает только свойства заливки фоновой фигуры. Все остальные свойства игнорируются.

Установка для этого свойства ненулевого значения также установит[`DisplayBackgroundShape`](../../../aspose.words.settings/viewoptions/displaybackgroundshape/) к истине.

### Примеры

Показывает, как установить форму фона для каждой страницы документа.

```csharp
Document doc = new Document();

Assert.IsNull(doc.BackgroundShape);

// Единственный тип фигуры, который мы можем использовать в качестве фона, — это прямоугольник.
Shape shapeRectangle = new Shape(doc, ShapeType.Rectangle);

// Есть два способа использования этой формы в качестве фона страницы.
// 1 - Плоский цвет:
shapeRectangle.FillColor = System.Drawing.Color.LightBlue;
doc.BackgroundShape = shapeRectangle;

doc.Save(ArtifactsDir + "DocumentBase.BackgroundShape.FlatColor.docx");

// 2 - Изображение:
shapeRectangle = new Shape(doc, ShapeType.Rectangle);
shapeRectangle.ImageData.SetImage(ImageDir + "Transparent background logo.png");

// Отрегулируйте внешний вид изображения, чтобы сделать его более подходящим для использования в качестве водяного знака.
shapeRectangle.ImageData.Contrast = 0.2;
shapeRectangle.ImageData.Brightness = 0.7;

doc.BackgroundShape = shapeRectangle;

Assert.IsTrue(doc.BackgroundShape.HasImage);

// Microsoft Word не поддерживает фигуры с изображениями в качестве фона,
// но мы все еще можем видеть эти фоны в других форматах сохранения, таких как .pdf.
doc.Save(ArtifactsDir + "DocumentBase.BackgroundShape.Image.pdf");
```

### Смотрите также

* class [Shape](../../../aspose.words.drawing/shape/)
* class [DocumentBase](../)
* пространство имен [Aspose.Words](../../documentbase/)
* сборка [Aspose.Words](../../../)


