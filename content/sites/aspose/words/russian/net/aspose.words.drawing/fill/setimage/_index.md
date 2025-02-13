---
title: Fill.SetImage
second_title: Справочник по API Aspose.Words для .NET
description: Fill метод. Изменяет тип заливки на одно изображение.
type: docs
weight: 190
url: /ru/net/aspose.words.drawing/fill/setimage/
---
## SetImage(string) {#setimage_2}

Изменяет тип заливки на одно изображение.

```csharp
public void SetImage(string fileName)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| fileName | String | Путь к файлу изображения. |

### Примеры

Показывает, как задать тип заливки фигуры как изображение.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Есть несколько способов установки изображения.
Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
// 1 - Использование локального системного имени файла:
shape.Fill.SetImage(ImageDir + "Logo.jpg");
doc.Save(ArtifactsDir + "Shape.FillImage.FileName.docx");

// 2 - Загрузить файл в массив байтов:
shape.Fill.SetImage(File.ReadAllBytes(ImageDir + "Logo.jpg"));
doc.Save(ArtifactsDir + "Shape.FillImage.ByteArray.docx");

// 3 - Из потока:
using (FileStream stream = new FileStream(ImageDir + "Logo.jpg", FileMode.Open))
    shape.Fill.SetImage(stream);
doc.Save(ArtifactsDir + "Shape.FillImage.Stream.docx");
```

### Смотрите также

* class [Fill](../)
* пространство имен [Aspose.Words.Drawing](../../fill/)
* сборка [Aspose.Words](../../../)

---

## SetImage(Stream) {#setimage_1}

Изменяет тип заливки на одно изображение.

```csharp
public void SetImage(Stream stream)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| stream | Stream | Поток, содержащий байты изображения. |

### Смотрите также

* class [Fill](../)
* пространство имен [Aspose.Words.Drawing](../../fill/)
* сборка [Aspose.Words](../../../)

---

## SetImage(byte[]) {#setimage}

Изменяет тип заливки на одно изображение.

```csharp
public void SetImage(byte[] imageBytes)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| imageBytes | Byte[] | Массив байтов изображения. |

### Смотрите также

* class [Fill](../)
* пространство имен [Aspose.Words.Drawing](../../fill/)
* сборка [Aspose.Words](../../../)


