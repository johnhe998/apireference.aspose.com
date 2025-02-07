---
title: EmfSetColorAdjustment Class
type: docs
weight: 1100
url: /python-net/aspose.imaging.fileformats.emf.emf.records/emfsetcoloradjustment/
---

The EMR_SETCOLORADJUSTMENT record specifies color adjustment properties in the playback<br/>            device context.

**Module:** [aspose.imaging.fileformats.emf.emf.records](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/)

**Full Name:** aspose.imaging.fileformats.emf.emf.records.EmfSetColorAdjustment

**Inheritance:** EmfStateRecordType

**Aspose.Imaging Version:** 23.6

The EmfSetColorAdjustment type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfSetColorAdjustment(source)](#EmfSetColorAdjustment_source_0) | Initializes a new instance of the [EmfSetColorAdjustment](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfsetcoloradjustment/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | r/w | Gets or sets the type. |
| size | int | r/w | Gets or sets the size of the record |
| color_adjustment | [EmfColorAdjustment](/imaging/python-net/aspose.imaging.fileformats.emf.emf.objects/emfcoloradjustment/) | r/w | Gets or sets a ColorAdjustment object (section 2.2.2) that specifies color<br/>            adjustment values. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [create_from_record(source)](#create_from_record_source_1) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |
| [create_from_type(type)](#create_from_type_type_2) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |

### EmfSetColorAdjustment(source) {#EmfSetColorAdjustment_source_0}


```
 EmfSetColorAdjustment(source) 
```

Initializes a new instance of the [EmfSetColorAdjustment](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfsetcoloradjustment/) class.

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


