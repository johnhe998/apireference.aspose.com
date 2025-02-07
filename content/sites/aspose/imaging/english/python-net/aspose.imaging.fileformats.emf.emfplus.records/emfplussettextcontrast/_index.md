---
title: EmfPlusSetTextContrast Class
type: docs
weight: 550
url: /python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplussettextcontrast/
---

The EmfPlusSetTextContrast record specifies text contrast according to the gamma correction value.

**Module:** [aspose.imaging.fileformats.emf.emfplus.records](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/)

**Full Name:** aspose.imaging.fileformats.emf.emfplus.records.EmfPlusSetTextContrast

**Inheritance:** EmfPlusPropertyRecordType

**Aspose.Imaging Version:** 23.6

The EmfPlusSetTextContrast type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfPlusSetTextContrast(source)](#EmfPlusSetTextContrast_source_0) | Initializes a new instance of the [EmfPlusSetTextContrast](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplussettextcontrast/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| type | [EmfPlusRecordType](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.consts/emfplusrecordtype/) | r | Gets a 16-bit unsigned integer that identifies the record type. |
| flags | short | r/w | Gets or sets a 16-bit unsigned integer that contains information for some records on how<br/>            the operation is to be performed and on the structure of the record. |
| size | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the 32-bit-aligned number of bytes<br/>            in the entire record, including the 12-byte record header and record-specific data. |
| data_size | int | r/w | Gets or sets a 32-bit unsigned integer that MUST define the 32-bit–aligned number of<br/>            bytes of data in the RecordData field that follows. This number does not include the 12-byte record header. |
| text_contrast | short | r/w | Gets or sets the gamma correction value X 1000, which will be applied to<br/>            subsequent text rendering operations. The allowable range is 1000 to 2200,<br/>            representing text gamma values of 1.0 to 2.2. |

### EmfPlusSetTextContrast(source) {#EmfPlusSetTextContrast_source_0}


```
 EmfPlusSetTextContrast(source) 
```

Initializes a new instance of the [EmfPlusSetTextContrast](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplussettextcontrast/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| source | [EmfPlusRecord](/imaging/python-net/aspose.imaging.fileformats.emf.emfplus.records/emfplusrecord) | The source. |

