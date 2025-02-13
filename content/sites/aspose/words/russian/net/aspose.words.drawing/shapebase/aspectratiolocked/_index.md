---
title: ShapeBase.AspectRatioLocked
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Указывает заблокировано ли соотношение сторон фигуры.
type: docs
weight: 40
url: /ru/net/aspose.words.drawing/shapebase/aspectratiolocked/
---
## ShapeBase.AspectRatioLocked property

Указывает, заблокировано ли соотношение сторон фигуры.

```csharp
public bool AspectRatioLocked { get; set; }
```

### Примечания

Значение по умолчанию зависит от[`ShapeType`](../shapetype/) , для ShapeType.Image это **истинный** , но для других типов фигур это **ЛОЖЬ**.

Действует только для фигур верхнего уровня.

### Примеры

Показывает, как заблокировать/разблокировать соотношение сторон фигуры.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставляем фигуру. Если мы откроем этот документ в Microsoft Word, мы можем щелкнуть левой кнопкой мыши по фигуре, чтобы открыть
// восемь маркеров изменения размера по периметру, которые мы можем щелкнуть и перетащить, чтобы изменить размер.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

// Установите для свойства "AspectRatioLocked" значение "true", чтобы сохранить соотношение сторон фигуры
// при использовании любого из четырех маркеров изменения размера по диагонали, которые изменяют как высоту, так и ширину изображения.
// Использование любых ортогональных маркеров изменения размера, которые изменяют высоту или ширину, по-прежнему будет изменять соотношение сторон.
// Установите для свойства "AspectRatioLocked" значение "false", чтобы мы могли
// свободно изменять соотношение сторон изображения со всеми маркерами изменения размера.
shape.AspectRatioLocked = lockAspectRatio;

doc.Save(ArtifactsDir + "Shape.AspectRatio.docx");
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


