---
title: EmfPlusFillPie Class
type: docs
weight: 260
url: /python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplusfillpie/
---

The EmfPlusFillPie record specifies filling a section of the interior of an ellipse

**Module:** [aspose.imaging.fileformats.emf.emfplus.records](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/)

**Full Name:** aspose.imaging.fileformats.emf.emfplus.records.EmfPlusFillPie

**Inheritance:** EmfPlusDrawingRecordType

**Aspose.Imaging Version:** 23.6

The EmfPlusFillPie type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfPlusFillPie(source)](#EmfPlusFillPie_source_0) | Initializes a new instance of the [EmfPlusFillPie](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplusfillpie/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfPlusRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.consts/emfplusrecordtype/) | r | Gets a 16-bit unsigned integer that identifies the record type. |
| flags | short | r/w | Gets or sets a 16-bit unsigned integer that contains information for some records on how<br/>            the operation is to be performed and on the structure of the record. |
| size | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the 32-bit-aligned number of bytes<br/>            in the entire record, including the 12-byte record header and record-specific data. |
| data_size | int | r/w | Gets or sets a 32-bit unsigned integer that MUST define the 32-bit–aligned number of<br/>            bytes of data in the RecordData field that follows. This number does not include the 12-byte record header. |
| compressed | bool | r/w | Gets or sets a value indicating whether the PointData is compressed.<br/>            If set, RectData contains an EmfPlusRect object (section 2.2.2.38).<br/>            If clear, RectData contains an EmfPlusRectF object (section 2.2.2.39). |
| is_color | bool | r/w | Gets or sets a value indicating whether this instance is color.<br/>            If set, BrushId specifies a color as an EmfPlusARGB object (section 2.2.2.1). <br/>            If clear, BrushId contains the index of an EmfPlusBrush object (section 2.2.1.1) in the EMF+ Object Table. |
| start_angle | float | r/w | Gets or sets the start angle<br/>            A 32-bit, non-negative floating-point value that specifies the angle between the <br/>            x-axis and the starting point of the pie wedge. Any value is acceptable, but it <br/>            MUST be interpreted modulo 360, with the result that is used being in the range <br/>            0.0 inclusive to 360.0 exclusive. |
| sweep_angle | float | r/w | Gets or sets the sweep angle<br/>            A 32-bit floating-point value that specifies the extent of the arc that defines <br/>            the pie wedge to draw, as an angle in degrees measured from the starting point <br/>            defined by the StartAngle value. Any value is acceptable, but it MUST be clamped <br/>            to -360.0 to 360.0 inclusive. A positive value indicates that the sweep is defined <br/>            in a clockwise direction, and a negative value indicates that the sweep is defined <br/>            in a counter-clockwise direction. |
| rect_data | [RectangleF](/imaging/python-net/aspose.imaging/rectanglef) | r/w | Gets or sets the rectangle datas<br/>            Either an EmfPlusRect or EmfPlusRectF object that defines the bounding box of the <br/>            ellipse that contains the pie wedge. This rectangle defines the position, size, <br/>            and shape of the pie. The type of object in this field is specified by the value <br/>            of the Flags field. |
| brush_id | int | r/w | Gets or sets the brush identifier<br/>            A 32-bit unsigned integer that defines the brush, the content of which <br/>            is determined by the S bit in the Flags field. |

### EmfPlusFillPie(source) {#EmfPlusFillPie_source_0}


```
 EmfPlusFillPie(source) 
```

Initializes a new instance of the [EmfPlusFillPie](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplusfillpie/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfPlusRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplusrecord) | The source. |

