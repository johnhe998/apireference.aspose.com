---
title: Description
second_title: Aspose.Slides for .NET API 参考
description: 返回摘要缩放部分对象的文本描述
type: docs
weight: 20
url: /zh/net/aspose.slides/isummaryzoomsection/description/
---
## ISummaryZoomSection.Description property

返回摘要缩放部分对象的文本描述。

```csharp
public string Description { get; set; }
```

### 例子

示例:

```csharp
[C#]
using (Presentation pres = new Presentation("pres.pptx"))
{
    ISummaryZoomSection zoomSection = zoomFrame.SummaryZoomCollection[1];
    zoomSection.Description = "Description";
}
```

### 也可以看看

* interface [ISummaryZoomSection](../../isummaryzoomsection)
* 命名空间 [Aspose.Slides](../../isummaryzoomsection)
* 部件 [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
