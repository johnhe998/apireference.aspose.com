---
title: Enum ImageType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.ImageType 枚举. 指定 Microsoft Word 文档中图像的类型格式
type: docs
weight: 950
url: /zh/net/aspose.words.drawing/imagetype/
---
## ImageType enumeration

指定 Microsoft Word 文档中图像的类型（格式）。

```csharp
public enum ImageType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| NoImage | `0` | 没有图像数据。 |
| Unknown | `1` | 无法直接存储在 Microsoft Word 文档中的未知图像类型或图像类型。 |
| Emf | `2` | Windows 增强元文件。 |
| Wmf | `3` | Windows 元文件。 |
| Pict | `4` | Macintosh PICT。现有图像将保留在文档中，但不支持将 new PICT 图像插入文档。 |
| Jpeg | `5` | JPEG JFIF. |
| Png | `6` | 便携式网络图形。 |
| Bmp | `7` | Windows 位图. |

### 例子

演示如何将图像添加到形状并检查其类型。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] imageBytes = File.ReadAllBytes(ImageDir + "Logo.jpg");

using (MemoryStream stream = new MemoryStream(imageBytes))
{
    Image image = Image.FromStream(stream);

    // URL 中的图片是 .gif。将其插入文档会将其转换为 .png。
    Shape imgShape = builder.InsertImage(image);
    Assert.AreEqual(ImageType.Jpeg, imgShape.ImageData.ImageType);
}
```

### 也可以看看

* property [ImageType](../imagedata/imagetype/)
* 命名空间 [Aspose.Words.Drawing](../../aspose.words.drawing/)
* 部件 [Aspose.Words](../../)


