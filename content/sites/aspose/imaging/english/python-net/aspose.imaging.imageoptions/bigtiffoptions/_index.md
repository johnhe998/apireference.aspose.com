---
title: BigTiffOptions Class
type: docs
weight: 20
url: /python-net/aspose.imaging.imageoptions/bigtiffoptions/
---

The BigTiff image options.

**Module:** [aspose.imaging.imageoptions](/imaging/python-net/aspose.imaging.imageoptions/)

**Full Name:** aspose.imaging.imageoptions.BigTiffOptions

**Inheritance:** TiffOptions

**Aspose.Imaging Version:** 23.6

The BigTiffOptions type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [BigTiffOptions(expected_format)](#BigTiffOptions_expected_format_0) | Initializes a new instance of the BigTiffOptions class |
| [BigTiffOptions(options)](#BigTiffOptions_options_1) | Initializes a new instance of the BigTiffOptions class |
| [BigTiffOptions(tags)](#BigTiffOptions_tags_2) | Initializes a new instance of the BigTiffOptions class |
| [BigTiffOptions(expected_format, byte_order)](#BigTiffOptions_expected_format_byte_order_3) | Initializes a new instance of the [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| disposed | bool | r | Gets a value indicating whether this instance is disposed. |
| xmp_data | [XmpPacketWrapper](/imaging/python-net/aspose.imaging.xmp/xmppacketwrapper/) | r/w | Gets or sets the XMP metadata container. |
| source | [Source](/imaging/python-net/aspose.imaging/source) | r/w | Gets or sets the source to create image in. |
| palette | [IColorPalette](/imaging/python-net/aspose.imaging/icolorpalette) | r/w | Gets or sets the color palette. |
| resolution_settings | [ResolutionSetting](/imaging/python-net/aspose.imaging/resolutionsetting) | r/w | Gets or sets the resolution settings. |
| vector_rasterization_options | [VectorRasterizationOptions](/imaging/python-net/aspose.imaging.imageoptions/vectorrasterizationoptions) | r/w | Gets or sets the vector rasterization options. |
| buffer_size_hint | int | r/w | Gets or sets the buffer size hint which is defined max allowed size for all internal buffers. |
| multi_page_options | [MultiPageOptions](/imaging/python-net/aspose.imaging.imageoptions/multipageoptions) | r/w | The multipage options |
| full_frame | bool | r/w | Gets or sets a value indicating whether [full frame]. |
| file_standard | [TiffFileStandards](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tifffilestandards/) | r/w | Gets or sets the TIFF file standard. |
| default_memory_allocation_limit | int | r/w | Gets or sets the default memory allocation limit. |
| premultiply_components | bool | r/w | Gets or sets a value indicating whether components must be premultiplied. |
| is_valid | bool | r | Gets a value indicating whether the [TiffOptions](/imaging/python-net/aspose.imaging.imageoptions/tiffoptions/) have been properly configured. Use Validate method as to find the failure reason. |
| y_cb_cr_subsampling | ushort | r/w | Gets or sets the subsampling factors for YCbCr photometric. |
| y_cb_cr_coefficients | [TiffRational[]](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffrational/) | r/w | Gets or sets the YCbCrCoefficients. |
| is_tiled | bool | r | Gets a value indicating whether image is tiled. |
| artist | string | r/w | Gets or sets the artist. |
| byte_order | [TiffByteOrder](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffbyteorder/) | r/w | Gets or sets a value indicating the tiff byte order. |
| disable_icc_export | bool | r/w | Gets or sets a value indicating whether ICC profile export is disabled (ICC profile is applied to the source pixels beforehand). |
| bits_per_sample | ushort | r/w | Gets or sets the bits per sample. |
| extra_samples | ushort | r | Gets the extra samples values. |
| compression | [TiffCompressions](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffcompressions/) | r/w | Gets or sets the compression. |
| compressed_quality | int | r/w | Gets or sets compressed image quality.<br/>            Used with the Jpeg compression. |
| copyright | string | r/w | Gets or sets the copyright. |
| color_map | ushort | r/w | Gets or sets the color map. |
| date_time | string | r/w | Gets or sets the date and time. |
| document_name | string | r/w | Gets or sets the name of the document. |
| alpha_storage | [TiffAlphaStorage](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffalphastorage/) | r/w | Gets or sets the alpha storage option. Options other than [UNSPECIFIED](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffalphastorage/)<br/>            are used when there are more than 3 [samples_per_pixel](/imaging/python-net/aspose.imaging.imageoptions/tiffoptions/) defined. |
| is_extra_samples_present | bool | r | Gets a value indicating whether the extra samples is present. |
| fill_order | [TiffFillOrders](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tifffillorders/) | r/w | Gets or sets the byte bits fill order. |
| half_tone_hints | ushort | r/w | Gets or sets the halftone hints. |
| image_description | string | r/w | Gets or sets the image description. |
| ink_names | string | r/w | Gets or sets the ink names. |
| scanner_manufacturer | string | r/w | Gets or sets the scanner manufacturer. |
| max_sample_value | ushort | r/w | Gets or sets the max sample value. |
| min_sample_value | ushort | r/w | Gets or sets the min sample value. |
| scanner_model | string | r/w | Gets or sets the scanner model. |
| orientation | [TiffOrientations](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tifforientations/) | r/w | Gets or sets the orientation. |
| page_name | string | r/w | Gets or sets the page name. |
| page_number | ushort | r/w | Gets or sets the page number tag. |
| photometric | [TiffPhotometrics](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffphotometrics/) | r/w | Gets or sets the photometric. |
| planar_configuration | [TiffPlanarConfigs](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffplanarconfigs/) | r/w | Gets or sets the planar configuration. |
| resolution_unit | [TiffResolutionUnits](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffresolutionunits/) | r/w | Gets or sets the resolution unit. |
| rows_per_strip | uint | r/w | Gets or sets the rows per strip. |
| tile_width | uint | r/w | Gets ot sets tile width. |
| tile_length | uint | r/w | Gets ot sets tile length. |
| sample_format | [TiffSampleFormats[]](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffsampleformats/) | r/w | Gets or sets the sample format. |
| samples_per_pixel | ushort | r | Gets the samples per pixel. To change this property value use the [bits_per_sample](/imaging/python-net/aspose.imaging.imageoptions/tiffoptions/) property setter. |
| smax_sample_value | uint | r/w | Gets or sets the max sample value. The value has a field type which best matches the sample data (Byte, Short or Long type). |
| smin_sample_value | uint | r/w | Gets or sets the min sample value. The value has a field type which best matches the sample data (Byte, Short or Long type). |
| software_type | string | r/w | Gets or sets the software type. |
| strip_byte_counts | ulong | r/w | Gets or sets the strip byte counts. |
| strip_offsets | ulong | r/w | Gets or sets the strip offsets. |
| tile_byte_counts | ulong | r/w | Gets or sets the tile byte counts. |
| tile_offsets | ulong | r/w | Gets or sets the tile offsets. |
| sub_file_type | [TiffNewSubFileTypes](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffnewsubfiletypes/) | r/w | Gets or sets a general indication of the kind of data contained in this subfile. |
| target_printer | string | r/w | Gets or sets the target printer. |
| threshholding | [TiffThresholds](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffthresholds/) | r/w | Gets or sets the threshholding. |
| total_pages | ushort | r | Gets the total pages. |
| xposition | [TiffRational](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffrational/) | r/w | Gets or sets the x position. |
| xresolution | [TiffRational](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffrational/) | r/w | Gets or sets the x resolution. |
| yposition | [TiffRational](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffrational/) | r/w | Gets or sets the y position. |
| yresolution | [TiffRational](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffrational/) | r/w | Gets or sets the y resolution. |
| fax_t4_options | [Group3Options](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/group3options/) | r/w | Gets or sets the fax t4 options. |
| predictor | [TiffPredictor](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffpredictor/) | r/w | Gets or sets the predictor for LZW compression. |
| image_length | uint | r/w | Gets or sets the image length. |
| image_width | uint | r/w | Gets or sets the image width. |
| exif_ifd | [TiffExifIfd](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffexififd/) | r | Gets or sets the pointer to EXIF IFD. |
| tags | [TiffDataType[]](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffdatatype/) | r/w | Gets or sets the tags. |
| valid_tag_count | int | r | Gets the valid tag count. This is not the total tags count but the number of tags which may be preserved. |
| bits_per_pixel | int | r | Gets the bits per pixel. |
| xp_title | string | r/w | Gets or sets information about image, which used by Windows Explorer. |
| xp_comment | string | r/w | Gets or sets comment on image, which used by Windows Explorer. |
| xp_author | string | r/w | Gets or sets image author, which used by Windows Explorer. |
| xp_keywords | string | r/w | Gets or sets subject image, which used by Windows Explorer. |
| xp_subject | string | r/w | Gets or sets information about image, which used by Windows Explorer. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [clone()](#clone__4) | Clones this instance. |
| [create_with_format(expected_format)](#create_with_format_expected_format_5) | Initializes a new instance of the [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions/) class. By default little endian convention is used. |
| [create_with_options(options)](#create_with_options_options_6) | Initializes a new instance of the [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions/) class. |
| [create_with_tags(tags)](#create_with_tags_tags_7) | Initializes a new instance of the [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions/) class. |
| [is_tag_present(tag)](#is_tag_present_tag_8) | Determines whether tag is present in the options or not. |
| [get_valid_tags_count(tags)](#get_valid_tags_count_tags_9) | Gets the valid tags count. |
| [remove_tag(tag)](#remove_tag_tag_10) | Removes the tag. |
| [remove_tags(tags)](#remove_tags_tags_11) | Removes the tags. |
| validate() | Validates if options have valid combination of tags |
| [add_tags(tags_to_add)](#add_tags_tags_to_add_12) | Adds the tags. |
| [add_tag(tag_to_add)](#add_tag_tag_to_add_13) | Adds a new tag. |
| [get_tag_by_type(tag_key)](#get_tag_by_type_tag_key_14) | Gets the instance of the tag by type. |

### BigTiffOptions(expected_format) {#BigTiffOptions_expected_format_0}


```
 BigTiffOptions(expected_format) 
```

Initializes a new instance of the BigTiffOptions class

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| expected_format | [TiffExpectedFormat](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffexpectedformat/) |  |

### BigTiffOptions(options) {#BigTiffOptions_options_1}


```
 BigTiffOptions(options) 
```

Initializes a new instance of the BigTiffOptions class

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| options | [TiffOptions](/imaging/python-net/aspose.imaging.imageoptions/tiffoptions) |  |

### BigTiffOptions(tags) {#BigTiffOptions_tags_2}


```
 BigTiffOptions(tags) 
```

Initializes a new instance of the BigTiffOptions class

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| tags | [TiffDataType[]](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffdatatype/) |  |

### BigTiffOptions(expected_format, byte_order) {#BigTiffOptions_expected_format_byte_order_3}


```
 BigTiffOptions(expected_format, byte_order) 
```

Initializes a new instance of the [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| expected_format | [TiffExpectedFormat](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffexpectedformat/) | The expected Tiff file format. |
| byte_order | [TiffByteOrder](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffbyteorder/) | The tiff file format byte order to use. |

### clone() {#clone__4}


```
 clone() 
```

Clones this instance.

**Returns**

| Type | Description |
| :- | :- |
| [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | Returns a deep clone. |


### create_with_format(expected_format)  [static] {#create_with_format_expected_format_5}


```
 create_with_format(expected_format) 
```

Initializes a new instance of the [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions/) class. By default little endian convention is used.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| expected_format | [TiffExpectedFormat](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tiffexpectedformat/) | The expected Tiff file format. |

**Returns**

| Type | Description |
| :- | :- |
| [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions) |  |


### create_with_options(options)  [static] {#create_with_options_options_6}


```
 create_with_options(options) 
```

Initializes a new instance of the [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| options | [TiffOptions](/imaging/python-net/aspose.imaging.imageoptions/tiffoptions) | The options source. |

**Returns**

| Type | Description |
| :- | :- |
| [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions) |  |


### create_with_tags(tags)  [static] {#create_with_tags_tags_7}


```
 create_with_tags(tags) 
```

Initializes a new instance of the [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| tags | [TiffDataType[]](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffdatatype/) | The tags for options initialization. |

**Returns**

| Type | Description |
| :- | :- |
| [BigTiffOptions](/imaging/python-net/aspose.imaging.imageoptions/bigtiffoptions) |  |


### is_tag_present(tag) {#is_tag_present_tag_8}


```
 is_tag_present(tag) 
```

Determines whether tag is present in the options or not.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| tag | [TiffTags](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tifftags/) | The tag id to check. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>true</c> if tag is present; otherwise, <c>false</c>. |


### get_valid_tags_count(tags)  [static] {#get_valid_tags_count_tags_9}


```
 get_valid_tags_count(tags) 
```

Gets the valid tags count.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| tags | [TiffDataType[]](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffdatatype/) | The tags to validate. |

**Returns**

| Type | Description |
| :- | :- |
| int | The valid tags count. |


### remove_tag(tag) {#remove_tag_tag_10}


```
 remove_tag(tag) 
```

Removes the tag.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| tag | [TiffTags](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tifftags/) | The tag to remove. |

**Returns**

| Type | Description |
| :- | :- |
| bool | true if successfully removed |


### remove_tags(tags) {#remove_tags_tags_11}


```
 remove_tags(tags) 
```

Removes the tags.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| tags | [TiffTags[]](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tifftags/) | The tags to remove. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <see langword="true" /> if tag collection size changed. |


### add_tags(tags_to_add) {#add_tags_tags_to_add_12}


```
 add_tags(tags_to_add) 
```

Adds the tags.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| tags_to_add | [TiffDataType[]](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffdatatype/) | The tags to add. |

### add_tag(tag_to_add) {#add_tag_tag_to_add_13}


```
 add_tag(tag_to_add) 
```

Adds a new tag.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| tag_to_add | [TiffDataType](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffdatatype/) | The tag to add. |

### get_tag_by_type(tag_key) {#get_tag_by_type_tag_key_14}


```
 get_tag_by_type(tag_key) 
```

Gets the instance of the tag by type.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| tag_key | [TiffTags](/imaging/python-net/aspose.imaging.fileformats.tiff.enums/tifftags/) | The tag key. |

**Returns**

| Type | Description |
| :- | :- |
| [TiffDataType](/imaging/python-net/aspose.imaging.fileformats.tiff/tiffdatatype/) | Instance of the tag if exists or null otherwise. |


