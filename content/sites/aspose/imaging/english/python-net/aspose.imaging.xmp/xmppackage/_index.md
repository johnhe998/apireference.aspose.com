---
title: XmpPackage Class
type: docs
weight: 440
url: /python-net/aspose.imaging.xmp/xmppackage/
---

Represents base abstraction for XMP package.

**Module:** [aspose.imaging.xmp](/imaging/python-net/aspose.imaging.xmp/)

**Full Name:** aspose.imaging.xmp.XmpPackage

**Inheritance:** IXmlValue

**Aspose.Imaging Version:** 23.6

The XmpPackage type exposes the following members:
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| xml_namespace | string | r | Gets the XML namespace. |
| prefix | string | r | Gets the prefix. |
| namespace_uri | string | r | Gets the namespace URI. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [contains_key(key)](#contains_key_key_0) | Determines whether the specified key contains key. |
| [get_prop_value(key)](#get_prop_value_key_1) | Gets the object with the specified key. |
| [set_prop_value(key, value)](#set_prop_value_key_value_2) | Gets or sets the object with the specified key. |
| [add_value(key, value)](#add_value_key_value_3) | Adds the value. |
| [remove(key)](#remove_key_4) | Remove the value with the specified key. |
| clear() | Clears this instance. |
| [set_value(key, value)](#set_value_key_value_5) | Sets the value. |
| [set_xmp_type_value(key, value)](#set_xmp_type_value_key_value_6) | Sets the XMP type value. |
| [get_xml_value()](#get_xml_value__7) | Converts XMP value to the XML representation. |

### contains_key(key) {#contains_key_key_0}


```
 contains_key(key) 
```

Determines whether the specified key contains key.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| key | string | The key to be checked. |

**Returns**

| Type | Description |
| :- | :- |
| bool | Returns true if the specified key contains key. |


### get_prop_value(key) {#get_prop_value_key_1}


```
 get_prop_value(key) 
```

Gets the object with the specified key.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| key | string | The key that identifies value. |

**Returns**

| Type | Description |
| :- | :- |
| object | Returns the object with the specified key. |


### set_prop_value(key, value) {#set_prop_value_key_value_2}


```
 set_prop_value(key, value) 
```

Gets or sets the object with the specified key.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| key | string | The key that identifies value. |
| value | object | The object with the specified key. |

### add_value(key, value) {#add_value_key_value_3}


```
 add_value(key, value) 
```

Adds the value.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| key | string | The string representation of key that is identified with added value. |
| value | string | The value to add to. |

### remove(key) {#remove_key_4}


```
 remove(key) 
```

Remove the value with the specified key.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| key | string | The string representation of key that is identified with removed value. |

**Returns**

| Type | Description |
| :- | :- |
| bool | Returns true if the value with the specified key was removed. |


### set_value(key, value) {#set_value_key_value_5}


```
 set_value(key, value) 
```

Sets the value.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| key | string | The string representation of key that is identified with added value. |
| value | [IXmlValue](/imaging/python-net/aspose.imaging.xmp/ixmlvalue) | The value to add to. |

### set_xmp_type_value(key, value) {#set_xmp_type_value_key_value_6}


```
 set_xmp_type_value(key, value) 
```

Sets the XMP type value.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| key | string | The string representation of key that is identified with set value. |
| value | [XmpTypeBase](/imaging/python-net/aspose.imaging.xmp.types/xmptypebase/) | The value to set to. |

### get_xml_value() {#get_xml_value__7}


```
 get_xml_value() 
```

Converts XMP value to the XML representation.

**Returns**

| Type | Description |
| :- | :- |
| string | Returns the XMP value converted to the XML representation. |


