---
title: EmfChord Class
type: docs
weight: 100
url: /python-net/aspose.imaging.fileformats.emf.emf.records/emfchord/
---

The EMR_CHORD record specifies a chord, which is a region bounded by the intersection of an <br/>            ellipse and a line segment, called a secant. The chord is outlined by using the current pen and filled <br/>            by using the current brush.

**Module:** [aspose.imaging.fileformats.emf.emf.records](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/)

**Full Name:** aspose.imaging.fileformats.emf.emf.records.EmfChord

**Inheritance:** EmfDrawingRecordType

**Aspose.Imaging Version:** 23.6

The EmfChord type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfChord(source)](#EmfChord_source_0) | Initializes a new instance of the [EmfChord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfchord/) class. |
| [EmfChord()](#EmfChord__1) | Initializes a new instance of the [EmfChord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfchord/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | r/w | Gets or sets the type. |
| size | int | r/w | Gets or sets the size of the record |
| box | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | r/w | Gets or sets a 128-bit WMF RectL object, specified in [MS-WMF] section 2.2.2.19, which <br/>            specifies the inclusive-inclusive bounding rectangle. |
| start | [Point](/imaging/python-net/aspose.imaging/point) | r/w | Gets or sets a 64-bit WMF PointL object, specified in [MS-WMF] section 2.2.2.15, which <br/>            specifies the logical coordinates of the endpoint of the radial defining the beginning of the chord. |
| end | [Point](/imaging/python-net/aspose.imaging/point) | r/w | Gets or sets a 64-bit WMF PointL object that specifies the logical coordinates of the <br/>            endpoint of the radial defining the end of the chord. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [create_from_record(source)](#create_from_record_source_2) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |
| [create_from_type(type)](#create_from_type_type_3) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |

### EmfChord(source) {#EmfChord_source_0}


```
 EmfChord(source) 
```

Initializes a new instance of the [EmfChord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfchord/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord) | The source. |

### EmfChord() {#EmfChord__1}


```
 EmfChord() 
```

Initializes a new instance of the [EmfChord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfchord/) class.

### create_from_record(source)  [static] {#create_from_record_source_2}


```
 create_from_record(source) 
```

Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord) | The source. |

**Returns**

| Type | Description |
| :- | :- |
| [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord) |  |


### create_from_type(type)  [static] {#create_from_type_type_3}


```
 create_from_type(type) 
```

Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | The record type. |

**Returns**

| Type | Description |
| :- | :- |
| [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord) |  |


