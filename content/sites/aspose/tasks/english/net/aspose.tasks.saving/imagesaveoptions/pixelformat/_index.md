---
title: PixelFormat
second_title: Aspose.Tasks for .NET API Reference
description: Gets or sets the format of the color data for each pixel in the image.
type: docs
weight: 80
url: /net/aspose.tasks.saving/imagesaveoptions/pixelformat/
---
## ImageSaveOptions.PixelFormat property

Gets or sets the format of the color data for each pixel in the image.

```csharp
public PixelFormat PixelFormat { get; set; }
```

### Examples

Shows how to set pixel format which is used during conversion into image formats.

```csharp
var project = new Project(DataDir + "Project1.mpp");
var options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.HorizontalResolution = 72;
options.VerticalResolution = 72;
options.PixelFormat = PixelFormat.Format24bppRgb;
project.Save(OutDir + "RenderProjectDataToFormat24bppRgb_out.tif", options);
```

### See Also

* class [ImageSaveOptions](../../imagesaveoptions)
* namespace [Aspose.Tasks.Saving](../../imagesaveoptions)
* assembly [Aspose.Tasks](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Tasks.dll -->
