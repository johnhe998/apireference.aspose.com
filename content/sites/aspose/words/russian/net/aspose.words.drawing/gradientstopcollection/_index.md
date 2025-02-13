---
title: Class GradientStopCollection
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Drawing.GradientStopCollection сорт. Содержит коллекциюGradientStop объекты.
type: docs
weight: 860
url: /ru/net/aspose.words.drawing/gradientstopcollection/
---
## GradientStopCollection class

Содержит коллекцию[`GradientStop`](../gradientstop/) объекты.

```csharp
public class GradientStopCollection : IEnumerable<GradientStop>
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Count](../../aspose.words.drawing/gradientstopcollection/count/) { get; } | Получает целочисленное значение, указывающее количество элементов в коллекции. |
| [Item](../../aspose.words.drawing/gradientstopcollection/item/) { get; set; } | Получает или задает[`GradientStop`](../gradientstop/) объект в коллекции. |

## Методы

| Имя | Описание |
| --- | --- |
| [Add](../../aspose.words.drawing/gradientstopcollection/add/)(GradientStop) | Добавляет указанный[`GradientStop`](../gradientstop/) к градиенту. |
| [GetEnumerator](../../aspose.words.drawing/gradientstopcollection/getenumerator/)() | Возвращает перечислитель, который выполняет итерацию по коллекции. |
| [Insert](../../aspose.words.drawing/gradientstopcollection/insert/)(int, GradientStop) | Вставляет[`GradientStop`](../gradientstop/) в коллекцию по указанному индексу. |
| [Remove](../../aspose.words.drawing/gradientstopcollection/remove/)(GradientStop) | Удаляет указанный[`GradientStop`](../gradientstop/) из коллекции. |
| [RemoveAt](../../aspose.words.drawing/gradientstopcollection/removeat/)(int) | Удаляет[`GradientStop`](../gradientstop/)из коллекции по указанному индексу. |

### Примечания

Вы не создаете экземпляры этого класса напрямую. Используйте[`GradientStops`](../fill/gradientstops/) свойство для доступа к остановкам градиента объектов заливки.

### Примеры

Показывает, как добавить остановки градиента к градиентной заливке.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
shape.Fill.TwoColorGradient(Color.Green, Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2);

// Получить коллекцию остановок градиента.
GradientStopCollection gradientStops = shape.Fill.GradientStops;

// Изменить первую точку градиента.
gradientStops[0].Color = Color.Aqua;
gradientStops[0].Position = 0.1;
gradientStops[0].Transparency = 0.25;

// Добавляем новую точку градиента в конец коллекции.
GradientStop gradientStop = new GradientStop(Color.Brown, 0.5);
gradientStops.Add(gradientStop);

// Удаляем остановку градиента по индексу 1.
gradientStops.RemoveAt(1);
// И вставляем новую точку градиента с тем же индексом 1.
gradientStops.Insert(1, new GradientStop(Color.Chocolate, 0.75, 0.3));

// Удалить последнюю остановку градиента в коллекции.
gradientStop = gradientStops[2];
gradientStops.Remove(gradientStop);

Assert.AreEqual(2, gradientStops.Count);

Assert.AreEqual(Color.Aqua.ToArgb(), gradientStops[0].Color.ToArgb());
Assert.AreEqual(0.1d, gradientStops[0].Position, 0.01d);
Assert.AreEqual(0.25d, gradientStops[0].Transparency, 0.01d);

Assert.AreEqual(Color.Chocolate.ToArgb(), gradientStops[1].Color.ToArgb());
Assert.AreEqual(0.75d, gradientStops[1].Position, 0.01d);
Assert.AreEqual(0.3d, gradientStops[1].Transparency, 0.01d);

// Используйте параметр соответствия для определения формы с помощью DML
// если вы хотите получить свойство "GradientStops" после сохранения документа.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientStops.docx", saveOptions);
```

### Смотрите также

* class [GradientStop](../gradientstop/)
* пространство имен [Aspose.Words.Drawing](../../aspose.words.drawing/)
* сборка [Aspose.Words](../../)


