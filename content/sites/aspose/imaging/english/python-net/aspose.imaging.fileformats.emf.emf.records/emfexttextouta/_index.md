---
title: EmfExtTextOutA Class
type: docs
weight: 460
url: /python-net/aspose.imaging.fileformats.emf.emf.records/emfexttextouta/
---

The EMR_EXTTEXTOUTA record draws an ASCII text string using the current font and text colors.

**Module:** [aspose.imaging.fileformats.emf.emf.records](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/)

**Full Name:** aspose.imaging.fileformats.emf.emf.records.EmfExtTextOutA

**Inheritance:** EmfDrawingRecordType

**Aspose.Imaging Version:** 23.6

The EmfExtTextOutA type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfExtTextOutA(source)](#EmfExtTextOutA_source_0) | Initializes a new instance of the [EmfExtTextOutA](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfexttextouta/) class. |
| [EmfExtTextOutA()](#EmfExtTextOutA__1) | Initializes a new instance of the [EmfExtTextOutA](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfexttextouta/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | r/w | Gets or sets the type. |
| size | int | r/w | Gets or sets the size of the record |
| bounds | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | r/w | Gets or sets a WMF RectL object ([MS-WMF] section 2.2.2.19). It is not used and <br/>            MUST be ignored on receipt. |
| graphics_mode | [EmfGraphicsMode](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfgraphicsmode/) | r/w | Gets or sets a 32-bit unsigned integer that specifies the graphics mode from the <br/>            GraphicsMode enumeration (section 2.1.16). |
| ex_scale | float | r/w | Gets or sets a 32-bit floating-point value that specifies the scale factor to apply along <br/>            the X axis to convert from page space units to .01mm units. This SHOULD be used only if the <br/>            graphics mode specified by iGraphicsMode is GM_COMPATIBLE. |
| ey_scale | float | r/w | Gets or sets a 32-bit floating-point value that specifies the scale factor to apply along <br/>            the Y axis to convert from page space units to .01mm units. This SHOULD be used only if the <br/>            graphics mode specified by iGraphicsMode is GM_COMPATIBLE. |
| a_emr_text | [EmfText](/imaging/python-net/aspose.imaging.fileformats.emf.emf.objects/emftext/) | r/w | Gets or sets an EmrText object (section 2.2.5) that specifies the output string in 8-bit <br/>            ASCII characters, text attributes, and spacing values. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [create_from_record(source)](#create_from_record_source_2) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |
| [create_from_type(type)](#create_from_type_type_3) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |

### EmfExtTextOutA(source) {#EmfExtTextOutA_source_0}


```
 EmfExtTextOutA(source) 
```

Initializes a new instance of the [EmfExtTextOutA](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfexttextouta/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord) | The source. |

### EmfExtTextOutA() {#EmfExtTextOutA__1}


```
 EmfExtTextOutA() 
```

Initializes a new instance of the [EmfExtTextOutA](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfexttextouta/) class.

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


