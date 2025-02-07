---
title: Class Config
second_title: Aspose.Cells for .NET API Reference
description: Aspose.Cells.GridJs.Config class. Represents all the settings for GridJs
type: docs
url: /net/aspose.cells.gridjs/config/
---
## Config class

Represents all the settings for GridJs

```csharp
public class Config
```

## Constructors

| Name | Description |
| --- | --- |
| [Config](config/)() | The default constructor. |

## Properties

| Name | Description |
| --- | --- |
| static [AutoOptimizeForLargeCells](../../aspose.cells.gridjs/config/autooptimizeforlargecells/) { get; set; } | Sets whether to automatically optimize the load performance for worksheet with large cells ignore some style /borders to reduce the load time the default value is true |
| static [EmptySheetMaxCol](../../aspose.cells.gridjs/config/emptysheetmaxcol/) { get; set; } | Sets/Gets default max column for an empty worksheet |
| static [EmptySheetMaxRow](../../aspose.cells.gridjs/config/emptysheetmaxrow/) { get; set; } | Sets default max row for an empty worksheet |
| static [FileCacheDirectory](../../aspose.cells.gridjs/config/filecachedirectory/) { get; set; } | Sets/Gets the cache directory for workbook file |
| static [IgnoreEmptyContent](../../aspose.cells.gridjs/config/ignoreemptycontent/) { get; set; } | Sets whether to show the max range which includes data ,style, merged cells and shapes. the default value is true .if the last row or column contains cells with no value and formula but has custom style then we will not show this row/column when this vlaue is true |
| static [IslimitShapeOrImage](../../aspose.cells.gridjs/config/islimitshapeorimage/) { get; set; } | Sets whether to limit the total display shape/image count inside one worksheet ,if set to true, GridJs will limit the total display shape/image size inside one worksheet to MaxShapeOrImageCount the default value is true |
| static [MaxPdfSaveSeconds](../../aspose.cells.gridjs/config/maxpdfsaveseconds/) { get; set; } | Sets /Gets the max timed out seconds when save to pdf |
| static [MaxShapeOrImageCount](../../aspose.cells.gridjs/config/maxshapeorimagecount/) { get; set; } | Sets /Gets the total display shape/image count inside the active sheet,it will take affec when IslimitShapes=true |
| static [MaxShapeOrImageWidthOrHeight](../../aspose.cells.gridjs/config/maxshapeorimagewidthorheight/) { get; set; } | Sets /Gets the max width or height for a shape/image ,GridJs will ignore the shape/image with the width or height larger than this, it will take affec when IslimitShapes=true |
| static [MaxTotalShapeOrImageCount](../../aspose.cells.gridjs/config/maxtotalshapeorimagecount/) { get; set; } | Sets /Gets the total display shape/image count inside the whole workbook,it will take affec when IslimitShapes=true |
| static [PageSize](../../aspose.cells.gridjs/config/pagesize/) { get; set; } | Sets whether to do pagination GridJs will limit the row size based on the PageSize,if PageSize is -1,it will not do pagination the default value is -1 |
| static [PictureCacheDirectory](../../aspose.cells.gridjs/config/picturecachedirectory/) { get; set; } | Sets/Gets the cache directory for pictures |
| static [SameImageDetecting](../../aspose.cells.gridjs/config/sameimagedetecting/) { get; set; } | Sets whether to check if picture has same source,the default is true the default value is true |
| static [SaveHtmlAsZip](../../aspose.cells.gridjs/config/savehtmlaszip/) { get; set; } | Sets whether to save html file as zip archive,the default is false |
| static [ShowChartSheet](../../aspose.cells.gridjs/config/showchartsheet/) { get; set; } | Sets whether to show chart worksheet. the default value is false . |
| static [UsePrintArea](../../aspose.cells.gridjs/config/useprintarea/) { get; set; } | Sets whether to use PageSetup.PrintArea for the UI display range when the worksheet has PageSetup setting for PrintArea. the default value is false . |

## Methods

| Name | Description |
| --- | --- |
| static [SetFontFolder](../../aspose.cells.gridjs/config/setfontfolder/)(string, bool) | Sets the fonts folder |
| static [SetFontFolders](../../aspose.cells.gridjs/config/setfontfolders/)(string[], bool) | Sets the fonts folders |

### See Also

* namespace [Aspose.Cells.GridJs](../../aspose.cells.gridjs/)
* assembly [Aspose.Cells.GridJs](../../)


