---
title: DocSaveOptions.AlwaysCompressMetafiles
linktitle: AlwaysCompressMetafiles
articleTitle: AlwaysCompressMetafiles
second_title: Aspose.Words for .NET
description: DocSaveOptions AlwaysCompressMetafiles property. When false small metafiles are not compressed for performance reason. Default value is true all metafiles are compressed regardless of its size in C#.
type: docs
weight: 20
url: /net/aspose.words.saving/docsaveoptions/alwayscompressmetafiles/
---
## DocSaveOptions.AlwaysCompressMetafiles property

When `false`, small metafiles are not compressed for performance reason. Default value is `true`, all metafiles are compressed regardless of its size.

```csharp
public bool AlwaysCompressMetafiles { get; set; }
```

## Examples

Shows how to change metafiles compression in a document while saving.

```csharp
// Open a document that contains a Microsoft Equation 3.0 formula.
Document doc = new Document(MyDir + "Microsoft equation object.docx");

// When we save a document, smaller metafiles are not compressed for performance reasons.
// We can set a flag in a SaveOptions object to compress every metafile when saving.
// Some editors such as LibreOffice cannot read uncompressed metafiles.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.AlwaysCompressMetafiles = compressAllMetafiles;

doc.Save(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx", saveOptions);

if (compressAllMetafiles)
    Assert.That(10000, Is.LessThan(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
else
    Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "DocSaveOptions.AlwaysCompressMetafiles.docx").Length));
```

### See Also

* class [DocSaveOptions](../)
* namespace [Aspose.Words.Saving](../../../aspose.words.saving/)
* assembly [Aspose.Words](../../../)
