---
title: EmfRegionDataHeader Class
type: docs
weight: 250
url: /python-net/aspose.imaging.fileformats.emf.emf.objects/emfregiondataheader/
---

The RegionDataHeader object describes the properties of a RegionData object.

**Module:** [aspose.imaging.fileformats.emf.emf.objects](/imaging/python-net/aspose.imaging.fileformats.emf.emf.objects/)

**Full Name:** aspose.imaging.fileformats.emf.emf.objects.EmfRegionDataHeader

**Inheritance:** EmfObject

**Aspose.Imaging Version:** 23.6

The EmfRegionDataHeader type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfRegionDataHeader()](#EmfRegionDataHeader__0) | Initializes a new instance of the EmfRegionDataHeader class |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| size | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the size of this object in bytes. This MUST be 0x00000020. |
| type | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the region type. This SHOULD be <br/>            RDH_RECTANGLES (0x00000001). |
| count_rects | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the number of rectangles in this region. |
| rgn_size | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the size of the buffer of rectangles in bytes. |
| bounds | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | r/w | Gets or sets a 128-bit WMF RectL object ([MS-WMF] section 2.2.2.19), which specifies <br/>            the bounds of the region. |

### EmfRegionDataHeader() {#EmfRegionDataHeader__0}


```
 EmfRegionDataHeader() 
```

Initializes a new instance of the EmfRegionDataHeader class

