---
title: EmfPlusSetPageTransform Class
type: docs
weight: 520
url: /python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplussetpagetransform/
---

The EmfPlusSetPageTransform record specifies scaling factors and units for converting page space<br/>            coordinates to device space coordinates.

**Module:** [aspose.imaging.fileformats.emf.emfplus.records](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/)

**Full Name:** aspose.imaging.fileformats.emf.emfplus.records.EmfPlusSetPageTransform

**Inheritance:** EmfPlusTerminalServerRecordType

**Aspose.Imaging Version:** 23.6

The EmfPlusSetPageTransform type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfPlusSetPageTransform(source)](#EmfPlusSetPageTransform_source_0) | Initializes a new instance of the [EmfPlusSetPageTransform](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplussetpagetransform/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfPlusRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.consts/emfplusrecordtype/) | r | Gets a 16-bit unsigned integer that identifies the record type. |
| flags | short | r/w | Gets or sets a 16-bit unsigned integer that contains information for some records on how<br/>            the operation is to be performed and on the structure of the record. |
| size | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the 32-bit-aligned number of bytes<br/>            in the entire record, including the 12-byte record header and record-specific data. |
| data_size | int | r/w | Gets or sets a 32-bit unsigned integer that MUST define the 32-bit–aligned number of<br/>            bytes of data in the RecordData field that follows. This number does not include the 12-byte record header. |
| page_unit | [EmfPlusUnitType](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.consts/emfplusunittype/) | r | Gets the unit of measure for page space coordinates, from the UnitType<br/>            enumeration (section 2.1.1.33). This value SHOULD NOT be UnitTypeDisplay or UnitTypeWorld. |
| page_scale | float | r/w | Gets or sets a 32-bit floating-point value that specifies the scale factor for converting<br/>            page space coordinates to device space coordinates. |

### EmfPlusSetPageTransform(source) {#EmfPlusSetPageTransform_source_0}


```
 EmfPlusSetPageTransform(source) 
```

Initializes a new instance of the [EmfPlusSetPageTransform](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplussetpagetransform/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfPlusRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplusrecord) | The source. |

