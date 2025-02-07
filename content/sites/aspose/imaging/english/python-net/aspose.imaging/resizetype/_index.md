---
title: ResizeType Enumeration
type: docs
weight: 10810
url: /python-net/aspose.imaging/resizetype/
---

Specifies the resize type.

**Module:** [aspose.imaging](/imaging/python-net/aspose.imaging/)

**Full Name:** aspose.imaging.ResizeType

**Aspose.Imaging Version:** 23.6

## **Members**
| **Member name** | **Description** |
| :- | :- |
| NONE | The pixels are not preserved during resize operation. |
| LEFT_TOP_TO_LEFT_TOP | Left top point of the new image will coincide with the left top point of the original image. Crop will occur if required. |
| RIGHT_TOP_TO_RIGHT_TOP | Right top point of the new image will coincide with the right top point of the original image. Crop will occur if required. |
| RIGHT_BOTTOM_TO_RIGHT_BOTTOM | Right bottom point of the new image will coincide with the right bottom point of the original image. Crop will occur if required. |
| LEFT_BOTTOM_TO_LEFT_BOTTOM | Left bottom point of the new image will coincide with the left bottom point of the original image. Crop will occur if required. |
| CENTER_TO_CENTER | Center of the new image will coincide with the center of the original image. Crop will occur if required. |
| LANCZOS_RESAMPLE | Resample using lanczos algorithm with a=3. |
| NEAREST_NEIGHBOUR_RESAMPLE | Resample using nearest neighbour algorithm. |
| ADAPTIVE_RESAMPLE | Resample using adaptive algorithm based on weighted and blended rational function and lanczos3 interpolation algorithms. |
| BILINEAR_RESAMPLE | Resample using bilinear interpolation. Image pre-filtering is allowed to remove the noice before resample, when needed |
| HIGH_QUALITY_RESAMPLE | The high quality resample |
| CATMULL_ROM | The Catmull-Rom cubic interpolation method. |
| CUBIC_CONVOLUTION | The Cubic Convolution interpolation method |
| CUBIC_B_SPLINE | The CubicBSpline cubic interpolation method |
| MITCHELL | The Mitchell cubic interpolation method |
| SIN_C | The Sinc (Lanczos3) cubic interpolation method |
| BELL | The Bell interpolation method |
