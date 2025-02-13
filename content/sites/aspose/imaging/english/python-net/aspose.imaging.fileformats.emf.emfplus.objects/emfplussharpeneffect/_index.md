---
title: EmfPlusSharpenEffect Class
type: docs
weight: 630
url: /python-net/aspose.imaging.fileformats.emf.emfplus.objects/emfplussharpeneffect/
---

The SharpenEffect object specifies an increase in the difference in intensity between pixels in an image.

**Module:** [aspose.imaging.fileformats.emf.emfplus.objects](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.objects/)

**Full Name:** aspose.imaging.fileformats.emf.emfplus.objects.EmfPlusSharpenEffect

**Inheritance:** EmfPlusImageEffectsObjectType

**Aspose.Imaging Version:** 23.6

The EmfPlusSharpenEffect type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfPlusSharpenEffect()](#EmfPlusSharpenEffect__0) | Initializes a new instance of the EmfPlusSharpenEffect class |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| radius | float | r/w | Gets or sets A 32-bit floating-point number that specifies the sharpening radius in pixels,<br/>            which determines the number of pixels involved in calculating the new value of a given pixel.<br/>            As this value increases, the number of pixels involved in the calculation increases, and the<br/>            resulting bitmap SHOULD become sharper. |
| amount | float | r/w | Gets or sets A 32-bit floating-point number that specifies the difference in intensity<br/>            between a given pixel and the surrounding pixels.<br/>            0 Specifies that sharpening MUST NOT be performed.<br/>            0 &lt; value ≤ 100<br/>            As this value increases, the difference in intensity between pixels SHOULD<br/>            increase. |

### EmfPlusSharpenEffect() {#EmfPlusSharpenEffect__0}


```
 EmfPlusSharpenEffect() 
```

Initializes a new instance of the EmfPlusSharpenEffect class

