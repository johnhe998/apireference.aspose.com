---
title: EmfPixelFormat Class
type: docs
weight: 730
url: /python-net/aspose.imaging.fileformats.emf.emf.records/emfpixelformat/
---

The EMR_PIXELFORMAT record specifies the pixel format to use for graphics operations.

**Module:** [aspose.imaging.fileformats.emf.emf.records](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/)

**Full Name:** aspose.imaging.fileformats.emf.emf.records.EmfPixelFormat

**Inheritance:** EmfStateRecordType

**Aspose.Imaging Version:** 23.6

The EmfPixelFormat type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfPixelFormat(source)](#EmfPixelFormat_source_0) | Initializes a new instance of the [EmfPixelFormat](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfpixelformat/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | r/w | Gets or sets the type. |
| size | int | r/w | Gets or sets the size of the record |
| pfd | [EmfPixelFormatDescriptor](/imaging/python-net/aspose.imaging.fileformats.emf.emf.objects/emfpixelformatdescriptor/) | r/w | Gets or sets a PixelFormatDescriptor object (section 2.2.22) that specifies pixel format data. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [create_from_record(source)](#create_from_record_source_1) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |
| [create_from_type(type)](#create_from_type_type_2) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |

### EmfPixelFormat(source) {#EmfPixelFormat_source_0}


```
 EmfPixelFormat(source) 
```

Initializes a new instance of the [EmfPixelFormat](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfpixelformat/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord) | The source. |

### create_from_record(source)  [static] {#create_from_record_source_1}


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


### create_from_type(type)  [static] {#create_from_type_type_2}


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


