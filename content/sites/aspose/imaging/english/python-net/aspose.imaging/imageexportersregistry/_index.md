---
title: ImageExportersRegistry Class
type: docs
weight: 5530
url: /python-net/aspose.imaging/imageexportersregistry/
---

Represents the image exporters registry.

**Module:** [aspose.imaging](/imaging/python-net/aspose.imaging/)

**Full Name:** aspose.imaging.ImageExportersRegistry

**Aspose.Imaging Version:** 23.6

The ImageExportersRegistry type exposes the following members:
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| registered_formats [static] | [FileFormat](/imaging/python-net/aspose.imaging/fileformat) | r | Gets the registered export formats. |
| registered_exporter_descriptors [static] | [IImageExporterDescriptor[]](/imaging/python-net/aspose.imaging/iimageexporterdescriptor) | r | Gets the registered exporter descriptors. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [register(image_exporter_descriptor)](#register_image_exporter_descriptor_0) | Registers the specified image exporter descriptor. |
| [get_first_supported_descriptor(image, options)](#get_first_supported_descriptor_image_options_1) | Gets the fist found supported descriptor suitable for the specified save options and image. |
| [create_first_supported_exporter(image, options)](#create_first_supported_exporter_image_options_2) | Creates the first found exporter suitable for the specified save options and image. |
| [register_exporter(exporter_descriptor)](#register_exporter_exporter_descriptor_3) | Registers the exporter. |
| [unregister_exporter(exporter_descriptor)](#unregister_exporter_exporter_descriptor_4) | Unregisters the exporter. |

### register(image_exporter_descriptor)  [static] {#register_image_exporter_descriptor_0}


```
 register(image_exporter_descriptor) 
```

Registers the specified image exporter descriptor.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| image_exporter_descriptor | [IImageExporterDescriptor](/imaging/python-net/aspose.imaging/iimageexporterdescriptor) | The image exporter descriptor. |

### get_first_supported_descriptor(image, options)  [static] {#get_first_supported_descriptor_image_options_1}


```
 get_first_supported_descriptor(image, options) 
```

Gets the fist found supported descriptor suitable for the specified save options and image.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| image | [Image](/imaging/python-net/aspose.imaging/image) | The image to export. |
| options | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The options. |

**Returns**

| Type | Description |
| :- | :- |
| [IImageExporterDescriptor](/imaging/python-net/aspose.imaging/iimageexporterdescriptor) | The exporter descriptor which supports the specified image and save options or null if no such descriptor is found. |


### create_first_supported_exporter(image, options)  [static] {#create_first_supported_exporter_image_options_2}


```
 create_first_supported_exporter(image, options) 
```

Creates the first found exporter suitable for the specified save options and image.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| image | [Image](/imaging/python-net/aspose.imaging/image) | The image to export. |
| options | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The save options to use for export. |

**Returns**

| Type | Description |
| :- | :- |
| [IImageExporter](/imaging/python-net/aspose.imaging/iimageexporter) | The exporter which supports the specified image and save options or null if no such exporter is found. |


### register_exporter(exporter_descriptor)  [static] {#register_exporter_exporter_descriptor_3}


```
 register_exporter(exporter_descriptor) 
```

Registers the exporter.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| exporter_descriptor | [IImageExporterDescriptor](/imaging/python-net/aspose.imaging/iimageexporterdescriptor) | The exporter descriptor to register. |

### unregister_exporter(exporter_descriptor)  [static] {#unregister_exporter_exporter_descriptor_4}


```
 unregister_exporter(exporter_descriptor) 
```

Unregisters the exporter.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| exporter_descriptor | [IImageExporterDescriptor](/imaging/python-net/aspose.imaging/iimageexporterdescriptor) | The exporter descriptor to unregister. |

