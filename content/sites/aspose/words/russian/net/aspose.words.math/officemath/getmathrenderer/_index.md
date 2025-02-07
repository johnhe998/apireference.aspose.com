---
title: OfficeMath.GetMathRenderer
second_title: Справочник по API Aspose.Words для .NET
description: OfficeMath метод. Создает и возвращает объект который можно использовать для преобразования этого уравнения в изображение.
type: docs
weight: 80
url: /ru/net/aspose.words.math/officemath/getmathrenderer/
---
## OfficeMath.GetMathRenderer method

Создает и возвращает объект, который можно использовать для преобразования этого уравнения в изображение.

```csharp
public OfficeMathRenderer GetMathRenderer()
```

### Возвращаемое значение

Объект визуализации для этого уравнения.

### Примечания

Этот метод просто вызывает[`OfficeMathRenderer`](../../../aspose.words.rendering/officemathrenderer/)конструктор и передает этот объект в качестве параметра.

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

* class [OfficeMathRenderer](../../../aspose.words.rendering/officemathrenderer/)
* class [OfficeMath](../)
* пространство имен [Aspose.Words.Math](../../officemath/)
* сборка [Aspose.Words](../../../)


