---
title: EmfCreatePen Class
type: docs
weight: 310
url: /python-net/aspose.imaging.fileformats.emf.emf.records/emfcreatepen/
---

The EMR_CREATEPEN record defines a logical pen for graphics operations.

**Module:** [aspose.imaging.fileformats.emf.emf.records](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/)

**Full Name:** aspose.imaging.fileformats.emf.emf.records.EmfCreatePen

**Inheritance:** EmfObjectCreationRecordType

**Aspose.Imaging Version:** 23.6

The EmfCreatePen type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfCreatePen(source)](#EmfCreatePen_source_0) | Initializes a new instance of the [EmfCreatePen](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfcreatepen/) class. |
| [EmfCreatePen()](#EmfCreatePen__1) | Initializes a new instance of the [EmfCreatePen](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfcreatepen/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | r/w | Gets or sets the type. |
| size | int | r/w | Gets or sets the size of the record |
| ih_pen | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the index of the logical pen object in<br/>            the EMF Object Table (section 3.1.1.1). This index MUST be saved so that this object can be<br/>            reused or modified. |
| log_pen | [EmfLogPen](/imaging/python-net/aspose.imaging.fileformats.emf.emf.objects/emflogpen/) | r/w | Gets or sets a LogPen object (section 2.2.19) that specifies the style, width, and color<br/>            of the logical pen. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [create_from_record(source)](#create_from_record_source_2) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |
| [create_from_type(type)](#create_from_type_type_3) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |

### EmfCreatePen(source) {#EmfCreatePen_source_0}


```
 EmfCreatePen(source) 
```

Initializes a new instance of the [EmfCreatePen](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfcreatepen/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord) | The source. |

### EmfCreatePen() {#EmfCreatePen__1}


```
 EmfCreatePen() 
```

Initializes a new instance of the [EmfCreatePen](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfcreatepen/) class.

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


