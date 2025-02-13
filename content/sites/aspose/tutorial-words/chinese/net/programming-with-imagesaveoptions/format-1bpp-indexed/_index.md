---
title: 格式 1Bpp 索引
linktitle: 格式 1Bpp 索引
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 1 bpp 中格式化使用 Aspose.Words for .NET 索引的图像。低色深图像的完整教程。
type: docs
weight: 10
url: /zh/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
在本教程中，我们将探索为 Aspose.Words for .NET 的“Format 1Bpp Indexed”功能提供的 C# 源代码。此功能允许您将文档中的图像格式化为 PNG 格式，颜色深度为每像素 1 位 (1 bpp) 和索引颜色模式。

## 第 1 步：设置环境

在您开始之前，请确保您已经使用 Aspose.Words for .NET 设置了您的开发环境。确保您已经添加了必要的引用并导入了适当的命名空间。

## 第 2 步：装入文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

在此步骤中，我们使用`Document`方法并将路径传递给要加载的 DOCX 文件。

## 第 3 步：配置映像备份选项

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

在此步骤中，我们为图像配置备份选项。我们创造一个新的`ImageSaveOptions`指定所需保存格式的对象，此处为 PNG 格式的“Png”。我们还定义了要包含在图像中的页面、黑白颜色模式和索引 1 bpp 像素格式。

## 第 4 步：备份图像

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

在这最后一步中，我们使用 PNG 格式保存文档图像`Save`方法并将路径传递到输出文件，以及指定的保存选项。

现在您可以运行源代码，将文档图像格式化为 PNG 格式，颜色深度为 1 bpp 索引。生成的文件将保存在指定目录中，名称为“WorkingWithImageSaveOptions.Format1BppIndexed.Png”。

### Format 1Bpp Indexed using Aspose.Words for .NET 的示例源代码

```csharp 
 
			 //文档目录的路径
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### 结论

在本教程中，我们探索了 Aspose.Words for .NET 的 1Bpp 索引格式功能。我们学习了如何以每像素 1 位 (1 bpp) 的颜色深度和索引颜色模式设置 PNG 格式文档中的图像格式。

当您想要获得颜色深度低且文件大小小的图像时，此功能很有用。 1Bpp 索引格式允许使用索引调色板表示图像，这对于某些特定应用程序可能是有益的。

Aspose.Words for .NET 为文档操作和生成提供了广泛的高级功能。 1Bpp 索引格式是它为您提供的众多强大工具之一。