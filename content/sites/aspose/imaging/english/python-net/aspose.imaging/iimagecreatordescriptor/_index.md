---
title: IImageCreatorDescriptor Class
type: docs
weight: 5160
url: /python-net/aspose.imaging/iimagecreatordescriptor/
---

The image creator descriptor specifying the creator properties. The creator descriptor is used to overcome<br/>            the necessity to contain each image creator instance in memory and multithreading issues.

**Module:** [aspose.imaging](/imaging/python-net/aspose.imaging/)

**Full Name:** aspose.imaging.IImageCreatorDescriptor

**Inheritance:** IImageDescriptor

**Aspose.Imaging Version:** 23.6

The IImageCreatorDescriptor type exposes the following members:
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| supported_format | [FileFormat](/imaging/python-net/aspose.imaging/fileformat) | r | Gets the supported format. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [can_create(image_options)](#can_create_image_options_0) | Determines whether image creator can create a new image using the <paramref name="imageOptions" />. |
| [create_instance()](#create_instance__1) | Creates a new creator instance. |

### can_create(image_options) {#can_create_image_options_0}


```
 can_create(image_options) 
```

Determines whether image creator can create a new image using the <paramref name="imageOptions" />.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| image_options | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The image options. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>True</c> if image creator created by this descriptor can create image data using the specified <paramref name="imageOptions" />; otherwise, <c>false</c>. |


### create_instance() {#create_instance__1}


```
 create_instance() 
```

Creates a new creator instance.

**Returns**

| Type | Description |
| :- | :- |
| [IImageCreator](/imaging/python-net/aspose.imaging/iimagecreator) | A new creator instance. |


