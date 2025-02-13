---
title: EmfColorCorrectPalette Class
type: docs
weight: 130
url: /python-net/aspose.imaging.fileformats.emf.emf.records/emfcolorcorrectpalette/
---

The EMR_COLORCORRECTPALETTE record specifies how to correct the entries of a logical palette<br/>            object using WCS 1.0 values.

**Module:** [aspose.imaging.fileformats.emf.emf.records](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/)

**Full Name:** aspose.imaging.fileformats.emf.emf.records.EmfColorCorrectPalette

**Inheritance:** EmfObjectManipulationRecordType

**Aspose.Imaging Version:** 23.6

The EmfColorCorrectPalette type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfColorCorrectPalette(source)](#EmfColorCorrectPalette_source_0) | Initializes a new instance of the [EmfColorCorrectPalette](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfcolorcorrectpalette/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | r/w | Gets or sets the type. |
| size | int | r/w | Gets or sets the size of the record |
| ih_palette | int | r/w | Gets or sets a 32-bit unsigned integer that specifies index of a logical palette object<br/>            (section 2.2.17) in the EMF Object Table (section 3.1.1.1). |
| n_first_entry | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the index of the first entry to correct. |
| n_pal_entries | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the number of palette entries to correct. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [create_from_record(source)](#create_from_record_source_1) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |
| [create_from_type(type)](#create_from_type_type_2) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |

### EmfColorCorrectPalette(source) {#EmfColorCorrectPalette_source_0}


```
 EmfColorCorrectPalette(source) 
```

Initializes a new instance of the [EmfColorCorrectPalette](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfcolorcorrectpalette/) class.

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


