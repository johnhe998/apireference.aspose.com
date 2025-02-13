---
title: EmfSetIcmProfileW Class
type: docs
weight: 1150
url: /python-net/aspose.imaging.fileformats.emf.emf.records/emfseticmprofilew/
---

The EMR_SETICMPROFILEW record specifies a color profile in a file with a name consisting of<br/>            Unicode characters, for graphics output.

**Module:** [aspose.imaging.fileformats.emf.emf.records](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/)

**Full Name:** aspose.imaging.fileformats.emf.emf.records.EmfSetIcmProfileW

**Inheritance:** EmfStateRecordType

**Aspose.Imaging Version:** 23.6

The EmfSetIcmProfileW type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfSetIcmProfileW(source)](#EmfSetIcmProfileW_source_0) | Initializes a new instance of the [EmfSetIcmProfileW](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfseticmprofilew/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | r/w | Gets or sets the type. |
| size | int | r/w | Gets or sets the size of the record |
| dw_flags | int | r/w | Gets or sets a 32-bit unsigned integer that contains color profile flags. |
| cb_name | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the number of bytes in the Unicode<br/>            UTF16-LE name of the desired color profile. |
| cb_data | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the size of color profile data, if attached. |
| data | byte | r/w | Gets or sets an array of size (cbName + cbData) in bytes, which specifies the UTF16-LE<br/>            name and raw data of the desired color profile. |
| name | string | r | Gets the name |
| raw_data | byte | r | Gets the raw data |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [create_from_record(source)](#create_from_record_source_1) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |
| [create_from_type(type)](#create_from_type_type_2) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |

### EmfSetIcmProfileW(source) {#EmfSetIcmProfileW_source_0}


```
 EmfSetIcmProfileW(source) 
```

Initializes a new instance of the [EmfSetIcmProfileW](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfseticmprofilew/) class.

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


