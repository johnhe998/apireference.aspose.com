---
title: IImageExporterDescriptor Class
type: docs
weight: 5190
url: /python-net/aspose.imaging/iimageexporterdescriptor/
---

Represents the image exporter descriptor. The exporter descriptor is used to overcome the necessity to contain each exporter instance<br/>            in memory and multithreading issues.

**Module:** [aspose.imaging](/imaging/python-net/aspose.imaging/)

**Full Name:** aspose.imaging.IImageExporterDescriptor

**Inheritance:** IImageDescriptor

**Aspose.Imaging Version:** 23.6

The IImageExporterDescriptor type exposes the following members:
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| supported_format | [FileFormat](/imaging/python-net/aspose.imaging/fileformat) | r | Gets the supported format. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [can_export(image, options_base)](#can_export_image_options_base_0) | Determines whether image exporter can export the specified image to the specified image format specified by save options. |
| [create_instance()](#create_instance__1) | Creates a new exporter instance. |

### can_export(image, options_base) {#can_export_image_options_base_0}


```
 can_export(image, options_base) 
```

Determines whether image exporter can export the specified image to the specified image format specified by save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| image | [Image](/imaging/python-net/aspose.imaging/image) | The image to export. |
| options_base | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The options base. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>True</c> if exporter created by this descriptor can export the specified image to the specified file format; otherwise, <c>false</c>. |


### create_instance() {#create_instance__1}


```
 create_instance() 
```

Creates a new exporter instance.

**Returns**

| Type | Description |
| :- | :- |
| [IImageExporter](/imaging/python-net/aspose.imaging/iimageexporter) | A new exporter instance. |


