---
title: WriteAsSvg
second_title: Aspose.Sildes for .NET API Reference
description: 
type: docs
weight: 140
url: /net/aspose.slides/slide/writeassvg/
---
## WriteAsSvg(Stream) {#writeassvg}

```csharp
public void WriteAsSvg(Stream stream)
```

### See Also

* class [Slide](../../slide)
* namespace [Aspose.Slides](../../slide)
* assembly [Aspose.Slides](../../../)

---

## WriteAsSvg(Stream, ISVGOptions) {#writeassvg_1}

Saves content of slide as SVG file.

```csharp
public void WriteAsSvg(Stream stream, ISVGOptions svgOptions)
```

| Parameter | Type | Description |
| --- | --- | --- |
| stream | Stream | Target stream |
| svgOptions | ISVGOptions | SVG generation options |

### Examples

The following example code shows how to generate SVG image with Custom Shape IDS from PowerPoint Presentation.

```csharp
// Instantiate a Presentation class that represents the presentation file
using (Presentation pres = new Presentation("CreateSlidesSVGImage.pptx"))
{
    // Access the first slide
    ISlide sld = pres.Slides[0];
    // Create a memory stream object
    MemoryStream SvgStream = new MemoryStream();
    // Generate SVG image of slide and save in memory stream
    sld.WriteAsSvg(SvgStream);
    SvgStream.Position = 0;
    // Save memory stream to file
    using (Stream fileStream = System.IO.File.OpenWrite("Aspose_out.svg"))
    {
        byte[] buffer = new byte[8 * 1024];
        int len;
        while ((len = SvgStream.Read(buffer, 0, buffer.Length)) > 0)
        {
            fileStream.Write(buffer, 0, len);
        }
    }
    SvgStream.Close();
}
```

### See Also

* interface [ISVGOptions](../../../aspose.slides.export/isvgoptions)
* class [Slide](../../slide)
* namespace [Aspose.Slides](../../slide)
* assembly [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
