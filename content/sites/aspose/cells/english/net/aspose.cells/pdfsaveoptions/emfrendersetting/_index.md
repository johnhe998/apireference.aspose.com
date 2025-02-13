---
title: PdfSaveOptions.EmfRenderSetting
second_title: Aspose.Cells for .NET API Reference
description: PdfSaveOptions property. Setting for rendering Emf metafile
type: docs
url: /net/aspose.cells/pdfsaveoptions/emfrendersetting/
---
## PdfSaveOptions.EmfRenderSetting property

Setting for rendering Emf metafile.

```csharp
public EmfRenderSetting EmfRenderSetting { get; set; }
```

### Remarks

EMF metafiles identified as "EMF+ Dual" can contain both EMF+ records and EMF records. Either type of record can be used to render the image, only EMF+ records, or only EMF records. When EmfPlusPrefer is set, then EMF+ records will be parsed while rendering to pdf, otherwise only EMF records will be parsed. Default value is EmfOnly.

### See Also

* enum [EmfRenderSetting](../../emfrendersetting/)
* class [PdfSaveOptions](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)


