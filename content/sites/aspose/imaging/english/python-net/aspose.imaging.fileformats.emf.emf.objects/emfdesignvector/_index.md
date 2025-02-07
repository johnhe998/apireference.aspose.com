---
title: EmfDesignVector Class
type: docs
weight: 40
url: /python-net/aspose.imaging.fileformats.emf.emf.objects/emfdesignvector/
---

The DesignVector (section 2.2.3) object defines the design vector, which specifies values for the font axes of a multiple master font.

**Module:** [aspose.imaging.fileformats.emf.emf.objects](/imaging/python-net/aspose.imaging.fileformats.emf.emf.objects/)

**Full Name:** aspose.imaging.fileformats.emf.emf.objects.EmfDesignVector

**Inheritance:** EmfObject

**Aspose.Imaging Version:** 23.6

The EmfDesignVector type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfDesignVector()](#EmfDesignVector__0) | Initializes a new instance of the EmfDesignVector class |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| signature | int | r/w | Gets or sets a 32-bit unsigned integer that MUST be set to the value 0x08007664. |
| num_axes | int | r/w | Gets or sets a 32-bit unsigned integer that specifies the number of elements in <br/>            the Values array. It MUST be in the range 0 to 16, inclusive |
| values | int | r/w | Gets or sets an optional array of 32-bit signed integers that specify the values <br/>            of the font axes of a multiple master, OpenType font. The maximum number of values in the array is 16. |

### EmfDesignVector() {#EmfDesignVector__0}


```
 EmfDesignVector() 
```

Initializes a new instance of the EmfDesignVector class

