---
title: EmfSetWindowExtEx Class
type: docs
weight: 1320
url: /python-net/aspose.imaging.fileformats.emf.emf.records/emfsetwindowextex/
---

The EMR_SETWINDOWEXTEX record defines the window extent.

**Module:** [aspose.imaging.fileformats.emf.emf.records](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/)

**Full Name:** aspose.imaging.fileformats.emf.emf.records.EmfSetWindowExtEx

**Inheritance:** EmfStateRecordType

**Aspose.Imaging Version:** 23.6

The EmfSetWindowExtEx type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfSetWindowExtEx(source)](#EmfSetWindowExtEx_source_0) | Initializes a new instance of the [EmfSetWindowExtEx](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfsetwindowextex/) class. |
| [EmfSetWindowExtEx()](#EmfSetWindowExtEx__1) | Initializes a new instance of the [EmfSetWindowExtEx](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfsetwindowextex/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | r/w | Gets or sets the type. |
| size | int | r/w | Gets or sets the size of the record |
| extent | [Size](/imaging/python-net/aspose.imaging/size) | r/w | Gets or sets a 64-bit WMF SizeL object ([MS-WMF] section 2.2.2.22) that specifies the<br/>            horizontal and vertical extents in logical units. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [create_from_record(source)](#create_from_record_source_2) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |
| [create_from_type(type)](#create_from_type_type_3) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |

### EmfSetWindowExtEx(source) {#EmfSetWindowExtEx_source_0}


```
 EmfSetWindowExtEx(source) 
```

Initializes a new instance of the [EmfSetWindowExtEx](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfsetwindowextex/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord) | The source. |

### EmfSetWindowExtEx() {#EmfSetWindowExtEx__1}


```
 EmfSetWindowExtEx() 
```

Initializes a new instance of the [EmfSetWindowExtEx](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfsetwindowextex/) class.

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


