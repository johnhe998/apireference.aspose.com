---
title: EmfExtSelectClipRgn Class
type: docs
weight: 450
url: /python-net/aspose.imaging.fileformats.emf.emf.records/emfextselectcliprgn/
---

The EMR_EXTSELECTCLIPRGN record combines the specified region with the current clip region <br/>            using the specified mode. <br/>            Note  Fields that are not described in this section are specified in section 2.3.2.

**Module:** [aspose.imaging.fileformats.emf.emf.records](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/)

**Full Name:** aspose.imaging.fileformats.emf.emf.records.EmfExtSelectClipRgn

**Inheritance:** EmfClippingRecordType

**Aspose.Imaging Version:** 23.6

The EmfExtSelectClipRgn type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfExtSelectClipRgn(source)](#EmfExtSelectClipRgn_source_0) | Initializes a new instance of the [EmfExtSelectClipRgn](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfextselectcliprgn/) class. |
| [EmfExtSelectClipRgn()](#EmfExtSelectClipRgn__1) | Initializes a new instance of the [EmfExtSelectClipRgn](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfextselectcliprgn/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfrecordtype/) | r/w | Gets or sets the type. |
| size | int | r/w | Gets or sets the size of the record |
| rgn_data_size | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the size of region data in bytes. |
| region_mode | [EmfRegionMode](/imaging/python-net/aspose.imaging.fileformats.emf.emf.consts/emfregionmode/) | r/w | Gets or sets a 32-bit unsigned integer that specifies the way to use the region. The <br/>            value MUST be in the RegionMode (section 2.1.29) enumeration. |
| rgn_data | [EmfRegionData](/imaging/python-net/aspose.imaging.fileformats.emf.emf.objects/emfregiondata/) | r/w | Gets or sets a RgnDataSize length array of bytes that specifies a RegionData object <br/>            in logical units. If RegionMode is RGN_COPY, this data can be omitted and the clip region <br/>            SHOULD be set to the default (NULL) clip region. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [create_from_record(source)](#create_from_record_source_2) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |
| [create_from_type(type)](#create_from_type_type_3) | Initializes a new instance of the [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord/) class. |

### EmfExtSelectClipRgn(source) {#EmfExtSelectClipRgn_source_0}


```
 EmfExtSelectClipRgn(source) 
```

Initializes a new instance of the [EmfExtSelectClipRgn](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfextselectcliprgn/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfrecord) | The source. |

### EmfExtSelectClipRgn() {#EmfExtSelectClipRgn__1}


```
 EmfExtSelectClipRgn() 
```

Initializes a new instance of the [EmfExtSelectClipRgn](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfextselectcliprgn/) class.

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


