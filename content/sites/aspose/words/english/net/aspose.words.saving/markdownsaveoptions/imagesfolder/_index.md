---
title: MarkdownSaveOptions.ImagesFolder
linktitle: ImagesFolder
articleTitle: ImagesFolder
second_title: Aspose.Words for .NET
description: MarkdownSaveOptions ImagesFolder property. Specifies the physical folder where images are saved when exporting a document to the Markdown format. Default is an empty string in C#.
type: docs
weight: 40
url: /net/aspose.words.saving/markdownsaveoptions/imagesfolder/
---
## MarkdownSaveOptions.ImagesFolder property

Specifies the physical folder where images are saved when exporting a document to the Markdown format. Default is an empty string.

```csharp
public string ImagesFolder { get; set; }
```

## Remarks

When you save a [`Document`](../../../aspose.words/document/) in Markdown format, Aspose.Words needs to save all images embedded in the document as standalone files. `ImagesFolder` allows you to specify where the images will be saved.

If you save a document into a file and provide a file name, Aspose.Words, by default, saves the images in the same folder where the document file is saved. Use `ImagesFolder` to override this behavior.

If you save a document into a stream, Aspose.Words does not have a folder where to save the images, but still needs to save the images somewhere. In this case, you need to specify an accessible folder in the `ImagesFolder` property.

If the folder specified by `ImagesFolder` doesn't exist, it will be created automatically.

### See Also

* class [MarkdownSaveOptions](../)
* namespace [Aspose.Words.Saving](../../../aspose.words.saving/)
* assembly [Aspose.Words](../../../)
