---
title: IPartialArgb64PixelLoader Class
type: docs
weight: 5350
url: /python-net/aspose.imaging/ipartialargb64pixelloader/
---

The 64-bit ARGB pixels loader.

**Module:** [aspose.imaging](/imaging/python-net/aspose.imaging/)

**Full Name:** aspose.imaging.IPartialArgb64PixelLoader

**Inheritance:** IPartialArgb32PixelLoader

**Aspose.Imaging Version:** 23.6

The IPartialArgb64PixelLoader type exposes the following members:
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [process64(pixels_rectangle, pixels, start, end)](#process64_pixels_rectangle_pixels_start_end_0) | Processes the loaded pixels. |
| [process(pixels_rectangle, pixels, start, end)](#process_pixels_rectangle_pixels_start_end_1) | Processes the loaded pixels. |

### process64(pixels_rectangle, pixels, start, end) {#process64_pixels_rectangle_pixels_start_end_0}


```
 process64(pixels_rectangle, pixels, start, end) 
```

Processes the loaded pixels.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| pixels_rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The pixels rectangle. |
| pixels | long | The 64-bit ARGB pixels. |
| start | [Point](/imaging/python-net/aspose.imaging/point) | The start pixels point. If not equal to (left,top) meaning that it is not full rectangle we have. |
| end | [Point](/imaging/python-net/aspose.imaging/point) | The end pixels point. If not equal to (right,bottom) meaning that it is not full rectangle we have. |

### process(pixels_rectangle, pixels, start, end) {#process_pixels_rectangle_pixels_start_end_1}


```
 process(pixels_rectangle, pixels, start, end) 
```

Processes the loaded pixels.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| pixels_rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The pixels rectangle. |
| pixels | int | The 64-bit ARGB pixels. |
| start | [Point](/imaging/python-net/aspose.imaging/point) | The start pixels point. If not equal to (left,top) meaning that it is not full rectangle we have. |
| end | [Point](/imaging/python-net/aspose.imaging/point) | The end pixels point. If not equal to (right,bottom) meaning that it is not full rectangle we have. |

