---
title: EmfLogPen Class
type: docs
weight: 180
url: /python-net/aspose.imaging.fileformats.emf.emf.objects/emflogpen/
---

The LogPen object defines the style, width, and color of a logical pen.

**Module:** [aspose.imaging.fileformats.emf.emf.objects](/imaging/python-net/aspose.imaging.fileformats.emf.emf.objects/)

**Full Name:** aspose.imaging.fileformats.emf.emf.objects.EmfLogPen

**Inheritance:** EmfBasePen

**Aspose.Imaging Version:** 23.6

The EmfLogPen type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfLogPen()](#EmfLogPen__0) | Initializes a new instance of the EmfLogPen class |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| pen_style | [EmfPenStyle](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfpenstyle/) | r/w | Gets or sets a 32-bit unsigned integer that specifies the PenStyle. The value MUST be <br/>            defined from the PenStyle enumeration table, specified in section 2.1.25. |
| argb_32_color_ref | int | r/w | Gets or sets a WMF ColorRef object ([MS-WMF] section 2.2.2.8) that specifies the pen color value. |
| width | [Point](/imaging/python-net/aspose.imaging/point) | r/w | Gets or sets a WMF PointL object ([MS-WMF] section 2.2.2.15) that specifies the width of <br/>            the pen by the value of its x field. The value of its y field MUST be ignored. |
| affect_width | int | r/w | Gets or sets the width of the affect. |

### EmfLogPen() {#EmfLogPen__0}


```
 EmfLogPen() 
```

Initializes a new instance of the EmfLogPen class

