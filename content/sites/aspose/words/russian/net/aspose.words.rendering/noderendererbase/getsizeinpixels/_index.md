---
title: NodeRendererBase.GetSizeInPixels
second_title: Справочник по API Aspose.Words для .NET
description: NodeRendererBase метод. Вычисляет размер фигуры в пикселях для указанного коэффициента масштабирования и разрешения.
type: docs
weight: 60
url: /ru/net/aspose.words.rendering/noderendererbase/getsizeinpixels/
---
## GetSizeInPixels(float, float) {#getsizeinpixels}

Вычисляет размер фигуры в пикселях для указанного коэффициента масштабирования и разрешения.

```csharp
public Size GetSizeInPixels(float scale, float dpi)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| scale | Single | Коэффициент масштабирования (1,0 соответствует 100%). |
| dpi | Single | Разрешение (горизонтальное и вертикальное) для преобразования точек в пиксели (точек на дюйм). |

### Возвращаемое значение

Размер фигуры в пикселях.

### Примечания

Этот метод преобразует[`SizeInPoints`](../sizeinpoints/) в размер в пикселях, и это полезно, , когда вы хотите создать растровое изображение для аккуратного рендеринга формы на растровое изображение.

### Примеры

Показывает, как измерять и масштабировать фигуры.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
OfficeMathRenderer renderer = new OfficeMathRenderer(officeMath);

// Проверяем размер изображения, которое объект OfficeMath создаст при его рендеринге.
Assert.AreEqual(119.0f, renderer.SizeInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.SizeInPoints.Height, 0.1f);

Assert.AreEqual(119.0f, renderer.BoundsInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.BoundsInPoints.Height, 0.1f);

// Формы с прозрачными частями могут содержать разные значения в свойствах "OpaqueBoundsInPoints".
Assert.AreEqual(119.0f, renderer.OpaqueBoundsInPoints.Width, 0.2f);
Assert.AreEqual(14.2f, renderer.OpaqueBoundsInPoints.Height, 0.1f);

// Получить размер фигуры в пикселях с линейным масштабированием до определенного DPI.
Rectangle bounds = renderer.GetBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

// Получаем размер фигуры в пикселях, но с разным DPI для горизонтального и вертикального размеров.
bounds = renderer.GetBoundsInPixels(1.0f, 96.0f, 150.0f);
Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(28, bounds.Height);

// Непрозрачные границы здесь тоже могут быть разными.
bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f, 150.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(30, bounds.Height);
```

### Смотрите также

* class [NodeRendererBase](../)
* пространство имен [Aspose.Words.Rendering](../../noderendererbase/)
* сборка [Aspose.Words](../../../)

---

## GetSizeInPixels(float, float, float) {#getsizeinpixels_1}

Вычисляет размер фигуры в пикселях для указанного коэффициента масштабирования и разрешения.

```csharp
public Size GetSizeInPixels(float scale, float horizontalDpi, float verticalDpi)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| scale | Single | Коэффициент масштабирования (1,0 соответствует 100%). |
| horizontalDpi | Single | Горизонтальное разрешение для преобразования точек в пиксели (точек на дюйм). |
| verticalDpi | Single | Вертикальное разрешение для преобразования точек в пиксели (точек на дюйм). |

### Возвращаемое значение

Размер фигуры в пикселях.

### Примечания

Этот метод преобразует[`SizeInPoints`](../sizeinpoints/) в размер в пикселях, и это полезно, , когда вы хотите создать растровое изображение для аккуратного рендеринга формы на растровое изображение.

### Примеры

Показывает, как измерять и масштабировать фигуры.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
OfficeMathRenderer renderer = new OfficeMathRenderer(officeMath);

// Проверяем размер изображения, которое объект OfficeMath создаст при его рендеринге.
Assert.AreEqual(119.0f, renderer.SizeInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.SizeInPoints.Height, 0.1f);

Assert.AreEqual(119.0f, renderer.BoundsInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.BoundsInPoints.Height, 0.1f);

// Формы с прозрачными частями могут содержать разные значения в свойствах "OpaqueBoundsInPoints".
Assert.AreEqual(119.0f, renderer.OpaqueBoundsInPoints.Width, 0.2f);
Assert.AreEqual(14.2f, renderer.OpaqueBoundsInPoints.Height, 0.1f);

// Получить размер фигуры в пикселях с линейным масштабированием до определенного DPI.
Rectangle bounds = renderer.GetBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

// Получаем размер фигуры в пикселях, но с разным DPI для горизонтального и вертикального размеров.
bounds = renderer.GetBoundsInPixels(1.0f, 96.0f, 150.0f);
Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(28, bounds.Height);

// Непрозрачные границы здесь тоже могут быть разными.
bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f, 150.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(30, bounds.Height);
```

### Смотрите также

* class [NodeRendererBase](../)
* пространство имен [Aspose.Words.Rendering](../../noderendererbase/)
* сборка [Aspose.Words](../../../)


