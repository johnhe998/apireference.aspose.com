---
title: EmfImage Class
type: docs
weight: 670
url: /python-net/aspose.imaging.fileformats.emf/emfimage/
---

EMF file format image.

**Module:** [aspose.imaging.fileformats.emf](/imaging/python-net/aspose.imaging.fileformats.emf/)

**Full Name:** aspose.imaging.fileformats.emf.EmfImage

**Inheritance:** IObjectWithBounds, IObjectWithSizeF, MetaImage

**Aspose.Imaging Version:** 23.6

The EmfImage type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [EmfImage()](#EmfImage__0) | Initializes a new instance of the [EmfImage](/imaging/python-net/aspose.imaging.fileformats.emf/emfimage/) class. |
| [EmfImage(width, height)](#EmfImage_width_height_1) | Initializes a new instance of the [EmfImage](/imaging/python-net/aspose.imaging.fileformats.emf/emfimage/) class. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| disposed | bool | r | Gets a value indicating whether this instance is disposed. |
| data_stream_container | [StreamContainer](/imaging/python-net/aspose.imaging/streamcontainer) | r | Gets the object's data stream. |
| is_cached | bool | r | Gets a value indicating whether object's data is cached currently and no data reading is required. |
| bits_per_pixel | int | r | Gets the image bits per pixel count this parameter is not applicable to vector images |
| bounds | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | r | Gets the object bounds. |
| container | [Image](/imaging/python-net/aspose.imaging/image) | r | Gets the [Image](/imaging/python-net/aspose.imaging/image/) container. |
| height | int | r | Gets the image height. |
| palette | [IColorPalette](/imaging/python-net/aspose.imaging/icolorpalette) | r/w | Gets or sets the color palette. The color palette is not used when pixels are represented directly. |
| use_palette | bool | r | Gets a value indicating whether the image palette is used. |
| size | [Size](/imaging/python-net/aspose.imaging/size) | r | Gets the object size. |
| width | int | r | Gets the image width. |
| interrupt_monitor | [InterruptMonitor](/imaging/python-net/aspose.imaging.multithreading/interruptmonitor/) | r/w | Gets or sets the interrupt monitor. |
| buffer_size_hint | int | r/w | Gets or sets the buffer size hint which is defined max allowed size for all internal buffers. |
| auto_adjust_palette | bool | r/w | Gets or sets a value indicating whether automatic adjust palette. |
| has_background_color | bool | r/w | Gets or sets a value indicating whether image has background color. |
| file_format | [FileFormat](/imaging/python-net/aspose.imaging/fileformat) | r | Gets a value of file format |
| background_color | [Color](/imaging/python-net/aspose.imaging/color) | r/w | Gets or sets a value for the background color. |
| size_f | [SizeF](/imaging/python-net/aspose.imaging/sizef) | r | Gets the object size, in inches. |
| width_f | float | r | Gets the object width, in inches. |
| height_f | float | r | Gets the object height, in inches. |
| records | [MetaObjectList](/imaging/python-net/aspose.imaging.fileformats.emf/metaobjectlist) | r/w | Gets or sets the records. |
| header | [EmfMetafileHeader](/imaging/python-net/aspose.imaging.fileformats.emf.emf.records/emfmetafileheader/) | r/w | Gets or sets the header record |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| save() | Saves the image data to the underlying stream. |
| [save(file_path)](#save_file_path_2) | Saves the image to the specified file location. |
| [save(file_path, options)](#save_file_path_options_3) | Saves the object's data to the specified file location in the specified file format according to save options. |
| [save(file_path, options, bounds_rectangle)](#save_file_path_options_bounds_rectangle_4) | Saves the object's data to the specified file location in the specified file format according to save options. |
| [save(stream, options_base)](#save_stream_options_base_5) | Saves the image's data to the specified stream in the specified file format according to save options. |
| [save(stream, options_base, bounds_rectangle)](#save_stream_options_base_bounds_rectangle_6) | Saves the image's data to the specified stream in the specified file format according to save options. |
| [save(stream)](#save_stream_7) | Saves the data. |
| [save(file_path, over_write)](#save_file_path_over_write_8) | Saves the object's data to the specified file location. |
| [can_load(file_path)](#can_load_file_path_9) | Determines whether image can be loaded from the specified file path. |
| [can_load(file_path, load_options)](#can_load_file_path_load_options_10) | Determines whether image can be loaded from the specified file path and optionally using the specified open options. |
| [can_load(stream)](#can_load_stream_11) | Determines whether image can be loaded from the specified stream. |
| [can_load(stream, load_options)](#can_load_stream_load_options_12) | Determines whether image can be loaded from the specified stream and optionally using the specified <paramref name="loadOptions" />. |
| [create(image_options, width, height)](#create_image_options_width_height_13) | Creates a new image using the specified create options. |
| [create(images)](#create_images_14) | Creates a new image using the specified images as pages |
| [create(images, dispose_images)](#create_images_dispose_images_15) | Creates a new image the specified images as pages. |
| [get_file_format(file_path)](#get_file_format_file_path_16) | Gets the file format. |
| [get_file_format(stream)](#get_file_format_stream_17) | Gets the file format. |
| [get_fitting_rectangle(rectangle, width, height)](#get_fitting_rectangle_rectangle_width_height_18) | Gets rectangle which fits the current image. |
| [get_fitting_rectangle(rectangle, pixels, width, height)](#get_fitting_rectangle_rectangle_pixels_width_height_19) | Gets rectangle which fits the current image. |
| [load(file_path, load_options)](#load_file_path_load_options_20) | Loads a new image from the specified file. |
| [load(file_path)](#load_file_path_21) | Loads a new image from the specified file. |
| [load(stream, load_options)](#load_stream_load_options_22) | Loads a new image from the specified stream. |
| [load(stream)](#load_stream_23) | Loads a new image from the specified stream. |
| [resize(new_width, new_height, resize_type)](#resize_new_width_new_height_resize_type_24) | Resizes the image. |
| [resize(new_width, new_height, settings)](#resize_new_width_new_height_settings_25) | Resizes the image. |
| [resize(new_width, new_height)](#resize_new_width_new_height_26) | Resizes the image. The default [NEAREST_NEIGHBOUR_RESAMPLE](/imaging/python-net/aspose.imaging/resizetype/) is used. |
| [resize_width_proportionally(new_width)](#resize_width_proportionally_new_width_27) | Resizes the width proportionally. The default [NEAREST_NEIGHBOUR_RESAMPLE](/imaging/python-net/aspose.imaging/resizetype/) is used. |
| [resize_width_proportionally(new_width, resize_type)](#resize_width_proportionally_new_width_resize_type_28) | Resizes the width proportionally. |
| [resize_width_proportionally(new_width, settings)](#resize_width_proportionally_new_width_settings_29) | Resizes the width proportionally. |
| [resize_height_proportionally(new_height)](#resize_height_proportionally_new_height_30) | Resizes the height proportionally. The default [NEAREST_NEIGHBOUR_RESAMPLE](/imaging/python-net/aspose.imaging/resizetype/) is used. |
| [resize_height_proportionally(new_height, resize_type)](#resize_height_proportionally_new_height_resize_type_31) | Resizes the height proportionally. |
| [resize_height_proportionally(new_height, settings)](#resize_height_proportionally_new_height_settings_32) | Resizes the height proportionally. |
| [crop(rectangle)](#crop_rectangle_33) | Crops the specified rectangle. |
| [crop(left_shift, right_shift, top_shift, bottom_shift)](#crop_left_shift_right_shift_top_shift_bottom_shift_34) | Crop image with shifts. |
| cache_data() | Caches the data and ensures no additional data loading will be performed from the underlying [data_stream_container](/imaging/python-net/aspose.imaging/datastreamsupporter/). |
| [save_to_stream(stream)](#save_to_stream_stream_35) | Saves the object's data to the specified stream. |
| [can_load_with_options(file_path, load_options)](#can_load_with_options_file_path_load_options_36) | Determines whether image can be loaded from the specified file path and optionally using the specified open options. |
| [can_load_stream(stream)](#can_load_stream_stream_37) | Determines whether image can be loaded from the specified stream. |
| [can_load_stream_with_options(stream, load_options)](#can_load_stream_with_options_stream_load_options_38) | Determines whether image can be loaded from the specified stream and optionally using the specified <paramref name="loadOptions" />. |
| [get_file_format_of_stream(stream)](#get_file_format_of_stream_stream_39) | Gets the file format. |
| [load_with_options(file_path, load_options)](#load_with_options_file_path_load_options_40) | Loads a new image from the specified file. |
| [load_stream_with_options(stream, load_options)](#load_stream_with_options_stream_load_options_41) | Loads a new image from the specified stream. |
| [load_stream(stream)](#load_stream_stream_42) | Loads a new image from the specified stream. |
| [can_save(options)](#can_save_options_43) | Determines whether image can be saved to the specified file format represented by the passed save options. |
| [resize_by_type(new_width, new_height, resize_type)](#resize_by_type_new_width_new_height_resize_type_44) | Resizes the image. |
| [resize_by_settings(new_width, new_height, settings)](#resize_by_settings_new_width_new_height_settings_45) | Resizes the image. |
| [get_default_options(args)](#get_default_options_args_46) | Gets the default options. |
| [get_original_options()](#get_original_options__47) | Gets the options based on the original file settings.<br/>            This can be helpful to keep bit-depth and other parameters of the original image unchanged.<br/>            For example, if we load a black-white PNG image with 1 bit per pixel and then save it using the<br/>            <see cref="M:Aspose.Imaging.DataStreamSupporter.Save(System.String)" /> method, the output PNG image with 8-bit per pixel will be produced.<br/>            To avoid it and save PNG image with 1-bit per pixel, use this method to get corresponding saving options and pass them<br/>            to the <see cref="M:Aspose.Imaging.Image.Save(System.String,Aspose.Imaging.ImageOptionsBase)" /> method as the second parameter. |
| [resize_width_proportionally_settings(new_width, settings)](#resize_width_proportionally_settings_new_width_settings_48) | Resizes the width proportionally. |
| [resize_height_proportionally_settings(new_height, settings)](#resize_height_proportionally_settings_new_height_settings_49) | Resizes the height proportionally. |
| [rotate_flip(rotate_flip_type)](#rotate_flip_rotate_flip_type_50) | Rotates, flips, or rotates and flips the image. |
| [save_with_options(file_path, options)](#save_with_options_file_path_options_51) | Saves the object's data to the specified file location in the specified file format according to save options. |
| [save_with_options_rect(file_path, options, bounds_rectangle)](#save_with_options_rect_file_path_options_bounds_rectangle_52) | Saves the object's data to the specified file location in the specified file format according to save options. |
| [save_to_stream_with_options(stream, options_base)](#save_to_stream_with_options_stream_options_base_53) | Saves the image's data to the specified stream in the specified file format according to save options. |
| [save_to_stream_with_options_rect(stream, options_base, bounds_rectangle)](#save_to_stream_with_options_rect_stream_options_base_bounds_rectangle_54) | Saves the image's data to the specified stream in the specified file format according to save options. |
| [set_palette(palette, update_colors)](#set_palette_palette_update_colors_55) | Sets the image palette. |
| [get_proportional_width(width, height, new_height)](#get_proportional_width_width_height_new_height_56) | Gets a proportional width. |
| [get_proportional_height(width, height, new_width)](#get_proportional_height_width_height_new_width_57) | Gets a proportional height. |
| [get_embedded_images()](#get_embedded_images__58) | Gets the embedded images. |
| [get_used_fonts()](#get_used_fonts__59) | Returns the list of font which used inside metafile. |
| [get_missed_fonts()](#get_missed_fonts__60) | Returns the list of fonts which used inside metafile but not found. |
| [resize_canvas(new_rectangle)](#resize_canvas_new_rectangle_61) | Resizes the canvas. |

### EmfImage() {#EmfImage__0}


```
 EmfImage() 
```

Initializes a new instance of the [EmfImage](/imaging/python-net/aspose.imaging.fileformats.emf/emfimage/) class.

### EmfImage(width, height) {#EmfImage_width_height_1}


```
 EmfImage(width, height) 
```

Initializes a new instance of the [EmfImage](/imaging/python-net/aspose.imaging.fileformats.emf/emfimage/) class.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| width | int | The width. |
| height | int | The height. |

### save(file_path) {#save_file_path_2}


```
 save(file_path) 
```

Saves the image to the specified file location.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path to save the image to. |

### save(file_path, options) {#save_file_path_options_3}


```
 save(file_path, options) 
```

Saves the object's data to the specified file location in the specified file format according to save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path. |
| options | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The options. |

### save(file_path, options, bounds_rectangle) {#save_file_path_options_bounds_rectangle_4}


```
 save(file_path, options, bounds_rectangle) 
```

Saves the object's data to the specified file location in the specified file format according to save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path. |
| options | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The options. |
| bounds_rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The destination image bounds rectangle. Set the empty rectangle for use sourse bounds. |

### save(stream, options_base) {#save_stream_options_base_5}


```
 save(stream, options_base) 
```

Saves the image's data to the specified stream in the specified file format according to save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to save the image's data to. |
| options_base | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The save options. |

### save(stream, options_base, bounds_rectangle) {#save_stream_options_base_bounds_rectangle_6}


```
 save(stream, options_base, bounds_rectangle) 
```

Saves the image's data to the specified stream in the specified file format according to save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to save the image's data to. |
| options_base | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The save options. |
| bounds_rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The destination image bounds rectangle. Set the empty rectangle for use source bounds. |

### save(stream) {#save_stream_7}


```
 save(stream) 
```

Saves the data.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to save data to. |

### save(file_path, over_write) {#save_file_path_over_write_8}


```
 save(file_path, over_write) 
```

Saves the object's data to the specified file location.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path to save the object's data to. |
| over_write | bool | if set to <c>true</c> over write the file contents, otherwise append will occur. |

### can_load(file_path)  [static] {#can_load_file_path_9}


```
 can_load(file_path) 
```

Determines whether image can be loaded from the specified file path.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>true</c> if image can be loaded from the specified file; otherwise, <c>false</c>. |


### can_load(file_path, load_options)  [static] {#can_load_file_path_load_options_10}


```
 can_load(file_path, load_options) 
```

Determines whether image can be loaded from the specified file path and optionally using the specified open options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path. |
| load_options | [LoadOptions](/imaging/python-net/aspose.imaging/loadoptions) | The load options. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>true</c> if image can be loaded from the specified file; otherwise, <c>false</c>. |


### can_load(stream)  [static] {#can_load_stream_11}


```
 can_load(stream) 
```

Determines whether image can be loaded from the specified stream.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to load from. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>true</c> if image can be loaded from the specified stream; otherwise, <c>false</c>. |


### can_load(stream, load_options)  [static] {#can_load_stream_load_options_12}


```
 can_load(stream, load_options) 
```

Determines whether image can be loaded from the specified stream and optionally using the specified <paramref name="loadOptions" />.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to load from. |
| load_options | [LoadOptions](/imaging/python-net/aspose.imaging/loadoptions) | The load options. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>true</c> if image can be loaded from the specified stream; otherwise, <c>false</c>. |


### create(image_options, width, height)  [static] {#create_image_options_width_height_13}


```
 create(image_options, width, height) 
```

Creates a new image using the specified create options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| image_options | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The image options. |
| width | int | The width. |
| height | int | The height. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The newly created image. |


### create(images)  [static] {#create_images_14}


```
 create(images) 
```

Creates a new image using the specified images as pages

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| images | [Image[]](/imaging/python-net/aspose.imaging/image) | The images. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The Image as IMultipageImage |


### create(images, dispose_images)  [static] {#create_images_dispose_images_15}


```
 create(images, dispose_images) 
```

Creates a new image the specified images as pages.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| images | [Image[]](/imaging/python-net/aspose.imaging/image) | The images. |
| dispose_images | bool | if set to <c>true</c> [dispose images]. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The Image as IMultipageImage |


### get_file_format(file_path)  [static] {#get_file_format_file_path_16}


```
 get_file_format(file_path) 
```

Gets the file format.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path. |

**Returns**

| Type | Description |
| :- | :- |
| [FileFormat](/imaging/python-net/aspose.imaging/fileformat) | The determined file format. |


### get_file_format(stream)  [static] {#get_file_format_stream_17}


```
 get_file_format(stream) 
```

Gets the file format.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream. |

**Returns**

| Type | Description |
| :- | :- |
| [FileFormat](/imaging/python-net/aspose.imaging/fileformat) | The determined file format. |


### get_fitting_rectangle(rectangle, width, height)  [static] {#get_fitting_rectangle_rectangle_width_height_18}


```
 get_fitting_rectangle(rectangle, width, height) 
```

Gets rectangle which fits the current image.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The rectangle to get fitting rectangle for. |
| width | int | The object width. |
| height | int | The object height. |

**Returns**

| Type | Description |
| :- | :- |
| [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The fitting rectangle or exception if no fitting rectangle can be found. |


### get_fitting_rectangle(rectangle, pixels, width, height)  [static] {#get_fitting_rectangle_rectangle_pixels_width_height_19}


```
 get_fitting_rectangle(rectangle, pixels, width, height) 
```

Gets rectangle which fits the current image.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The rectangle to get fitting rectangle for. |
| pixels | int | The 32-bit ARGB pixels. |
| width | int | The object width. |
| height | int | The object height. |

**Returns**

| Type | Description |
| :- | :- |
| [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The fitting rectangle or exception if no fitting rectangle can be found. |


### load(file_path, load_options)  [static] {#load_file_path_load_options_20}


```
 load(file_path, load_options) 
```

Loads a new image from the specified file.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path to load image from. |
| load_options | [LoadOptions](/imaging/python-net/aspose.imaging/loadoptions) | The load options. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The loaded image. |


### load(file_path)  [static] {#load_file_path_21}


```
 load(file_path) 
```

Loads a new image from the specified file.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path to load image from. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The loaded image. |


### load(stream, load_options)  [static] {#load_stream_load_options_22}


```
 load(stream, load_options) 
```

Loads a new image from the specified stream.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to load image from. |
| load_options | [LoadOptions](/imaging/python-net/aspose.imaging/loadoptions) | The load options. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The loaded image. |


### load(stream)  [static] {#load_stream_23}


```
 load(stream) 
```

Loads a new image from the specified stream.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to load image from. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The loaded image. |


### resize(new_width, new_height, resize_type) {#resize_new_width_new_height_resize_type_24}


```
 resize(new_width, new_height, resize_type) 
```

Resizes the image.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_width | int | The new width. |
| new_height | int | The new height. |
| resize_type | [ResizeType](/imaging/python-net/aspose.imaging/resizetype) | The resize type. |

### resize(new_width, new_height, settings) {#resize_new_width_new_height_settings_25}


```
 resize(new_width, new_height, settings) 
```

Resizes the image.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_width | int | The new width. |
| new_height | int | The new height. |
| settings | [ImageResizeSettings](/imaging/python-net/aspose.imaging/imageresizesettings) | The resize settings. |

### resize(new_width, new_height) {#resize_new_width_new_height_26}


```
 resize(new_width, new_height) 
```

Resizes the image. The default [NEAREST_NEIGHBOUR_RESAMPLE](/imaging/python-net/aspose.imaging/resizetype/) is used.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_width | int | The new width. |
| new_height | int | The new height. |

### resize_width_proportionally(new_width) {#resize_width_proportionally_new_width_27}


```
 resize_width_proportionally(new_width) 
```

Resizes the width proportionally. The default [NEAREST_NEIGHBOUR_RESAMPLE](/imaging/python-net/aspose.imaging/resizetype/) is used.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_width | int | The new width. |

### resize_width_proportionally(new_width, resize_type) {#resize_width_proportionally_new_width_resize_type_28}


```
 resize_width_proportionally(new_width, resize_type) 
```

Resizes the width proportionally.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_width | int | The new width. |
| resize_type | [ResizeType](/imaging/python-net/aspose.imaging/resizetype) | Type of the resize. |

### resize_width_proportionally(new_width, settings) {#resize_width_proportionally_new_width_settings_29}


```
 resize_width_proportionally(new_width, settings) 
```

Resizes the width proportionally.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_width | int | The new width. |
| settings | [ImageResizeSettings](/imaging/python-net/aspose.imaging/imageresizesettings) | The image resize settings. |

### resize_height_proportionally(new_height) {#resize_height_proportionally_new_height_30}


```
 resize_height_proportionally(new_height) 
```

Resizes the height proportionally. The default [NEAREST_NEIGHBOUR_RESAMPLE](/imaging/python-net/aspose.imaging/resizetype/) is used.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_height | int | The new height. |

### resize_height_proportionally(new_height, resize_type) {#resize_height_proportionally_new_height_resize_type_31}


```
 resize_height_proportionally(new_height, resize_type) 
```

Resizes the height proportionally.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_height | int | The new height. |
| resize_type | [ResizeType](/imaging/python-net/aspose.imaging/resizetype) | Type of the resize. |

### resize_height_proportionally(new_height, settings) {#resize_height_proportionally_new_height_settings_32}


```
 resize_height_proportionally(new_height, settings) 
```

Resizes the height proportionally.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_height | int | The new height. |
| settings | [ImageResizeSettings](/imaging/python-net/aspose.imaging/imageresizesettings) | The image resize settings. |

### crop(rectangle) {#crop_rectangle_33}


```
 crop(rectangle) 
```

Crops the specified rectangle.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The rectangle. |

### crop(left_shift, right_shift, top_shift, bottom_shift) {#crop_left_shift_right_shift_top_shift_bottom_shift_34}


```
 crop(left_shift, right_shift, top_shift, bottom_shift) 
```

Crop image with shifts.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| left_shift | int | The left shift. |
| right_shift | int | The right shift. |
| top_shift | int | The top shift. |
| bottom_shift | int | The bottom shift. |

### save_to_stream(stream) {#save_to_stream_stream_35}


```
 save_to_stream(stream) 
```

Saves the object's data to the specified stream.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to save the object's data to. |

### can_load_with_options(file_path, load_options)  [static] {#can_load_with_options_file_path_load_options_36}


```
 can_load_with_options(file_path, load_options) 
```

Determines whether image can be loaded from the specified file path and optionally using the specified open options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path. |
| load_options | [LoadOptions](/imaging/python-net/aspose.imaging/loadoptions) | The load options. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>true</c> if image can be loaded from the specified file; otherwise, <c>false</c>. |


### can_load_stream(stream)  [static] {#can_load_stream_stream_37}


```
 can_load_stream(stream) 
```

Determines whether image can be loaded from the specified stream.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to load from. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>true</c> if image can be loaded from the specified stream; otherwise, <c>false</c>. |


### can_load_stream_with_options(stream, load_options)  [static] {#can_load_stream_with_options_stream_load_options_38}


```
 can_load_stream_with_options(stream, load_options) 
```

Determines whether image can be loaded from the specified stream and optionally using the specified <paramref name="loadOptions" />.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to load from. |
| load_options | [LoadOptions](/imaging/python-net/aspose.imaging/loadoptions) | The load options. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>true</c> if image can be loaded from the specified stream; otherwise, <c>false</c>. |


### get_file_format_of_stream(stream)  [static] {#get_file_format_of_stream_stream_39}


```
 get_file_format_of_stream(stream) 
```

Gets the file format.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream. |

**Returns**

| Type | Description |
| :- | :- |
| [FileFormat](/imaging/python-net/aspose.imaging/fileformat) | The determined file format. |


### load_with_options(file_path, load_options)  [static] {#load_with_options_file_path_load_options_40}


```
 load_with_options(file_path, load_options) 
```

Loads a new image from the specified file.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path to load image from. |
| load_options | [LoadOptions](/imaging/python-net/aspose.imaging/loadoptions) | The load options. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The loaded image. |


### load_stream_with_options(stream, load_options)  [static] {#load_stream_with_options_stream_load_options_41}


```
 load_stream_with_options(stream, load_options) 
```

Loads a new image from the specified stream.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to load image from. |
| load_options | [LoadOptions](/imaging/python-net/aspose.imaging/loadoptions) | The load options. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The loaded image. |


### load_stream(stream)  [static] {#load_stream_stream_42}


```
 load_stream(stream) 
```

Loads a new image from the specified stream.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to load image from. |

**Returns**

| Type | Description |
| :- | :- |
| [Image](/imaging/python-net/aspose.imaging/image) | The loaded image. |


### can_save(options) {#can_save_options_43}


```
 can_save(options) 
```

Determines whether image can be saved to the specified file format represented by the passed save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| options | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The save options to use. |

**Returns**

| Type | Description |
| :- | :- |
| bool | <c>true</c> if image can be saved to the specified file format represented by the passed save options; otherwise, <c>false</c>. |


### resize_by_type(new_width, new_height, resize_type) {#resize_by_type_new_width_new_height_resize_type_44}


```
 resize_by_type(new_width, new_height, resize_type) 
```

Resizes the image.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_width | int | The new width. |
| new_height | int | The new height. |
| resize_type | [ResizeType](/imaging/python-net/aspose.imaging/resizetype) | The resize type. |

### resize_by_settings(new_width, new_height, settings) {#resize_by_settings_new_width_new_height_settings_45}


```
 resize_by_settings(new_width, new_height, settings) 
```

Resizes the image.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_width | int | The new width. |
| new_height | int | The new height. |
| settings | [ImageResizeSettings](/imaging/python-net/aspose.imaging/imageresizesettings) | The resize settings. |

### get_default_options(args) {#get_default_options_args_46}


```
 get_default_options(args) 
```

Gets the default options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| args | object | The arguments. |

**Returns**

| Type | Description |
| :- | :- |
| [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | Default options |


### get_original_options() {#get_original_options__47}


```
 get_original_options() 
```

Gets the options based on the original file settings.<br/>            This can be helpful to keep bit-depth and other parameters of the original image unchanged.<br/>            For example, if we load a black-white PNG image with 1 bit per pixel and then save it using the<br/>            <see cref="M:Aspose.Imaging.DataStreamSupporter.Save(System.String)" /> method, the output PNG image with 8-bit per pixel will be produced.<br/>            To avoid it and save PNG image with 1-bit per pixel, use this method to get corresponding saving options and pass them<br/>            to the <see cref="M:Aspose.Imaging.Image.Save(System.String,Aspose.Imaging.ImageOptionsBase)" /> method as the second parameter.

**Returns**

| Type | Description |
| :- | :- |
| [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The options based on the original file settings. |


### resize_width_proportionally_settings(new_width, settings) {#resize_width_proportionally_settings_new_width_settings_48}


```
 resize_width_proportionally_settings(new_width, settings) 
```

Resizes the width proportionally.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_width | int | The new width. |
| settings | [ImageResizeSettings](/imaging/python-net/aspose.imaging/imageresizesettings) | The image resize settings. |

### resize_height_proportionally_settings(new_height, settings) {#resize_height_proportionally_settings_new_height_settings_49}


```
 resize_height_proportionally_settings(new_height, settings) 
```

Resizes the height proportionally.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_height | int | The new height. |
| settings | [ImageResizeSettings](/imaging/python-net/aspose.imaging/imageresizesettings) | The image resize settings. |

### rotate_flip(rotate_flip_type) {#rotate_flip_rotate_flip_type_50}


```
 rotate_flip(rotate_flip_type) 
```

Rotates, flips, or rotates and flips the image.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rotate_flip_type | [RotateFlipType](/imaging/python-net/aspose.imaging/rotatefliptype) | Type of the rotate flip. |

### save_with_options(file_path, options) {#save_with_options_file_path_options_51}


```
 save_with_options(file_path, options) 
```

Saves the object's data to the specified file location in the specified file format according to save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path. |
| options | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The options. |

### save_with_options_rect(file_path, options, bounds_rectangle) {#save_with_options_rect_file_path_options_bounds_rectangle_52}


```
 save_with_options_rect(file_path, options, bounds_rectangle) 
```

Saves the object's data to the specified file location in the specified file format according to save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| file_path | string | The file path. |
| options | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The options. |
| bounds_rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The destination image bounds rectangle. Set the empty rectangle for use sourse bounds. |

### save_to_stream_with_options(stream, options_base) {#save_to_stream_with_options_stream_options_base_53}


```
 save_to_stream_with_options(stream, options_base) 
```

Saves the image's data to the specified stream in the specified file format according to save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to save the image's data to. |
| options_base | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The save options. |

### save_to_stream_with_options_rect(stream, options_base, bounds_rectangle) {#save_to_stream_with_options_rect_stream_options_base_bounds_rectangle_54}


```
 save_to_stream_with_options_rect(stream, options_base, bounds_rectangle) 
```

Saves the image's data to the specified stream in the specified file format according to save options.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| stream | _io.BufferedRandom | The stream to save the image's data to. |
| options_base | [ImageOptionsBase](/imaging/python-net/aspose.imaging/imageoptionsbase) | The save options. |
| bounds_rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The destination image bounds rectangle. Set the empty rectangle for use source bounds. |

### set_palette(palette, update_colors) {#set_palette_palette_update_colors_55}


```
 set_palette(palette, update_colors) 
```

Sets the image palette.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| palette | [IColorPalette](/imaging/python-net/aspose.imaging/icolorpalette) | The palette to set. |
| update_colors | bool | if set to <c>true</c> colors will be updated according to the new palette; otherwise color indexes remain unchanged. Note that unchanged indexes may crash the image on loading if some indexes have no corresponding palette entries. |

### get_proportional_width(width, height, new_height)  [static] {#get_proportional_width_width_height_new_height_56}


```
 get_proportional_width(width, height, new_height) 
```

Gets a proportional width.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| width | int | The width. |
| height | int | The height. |
| new_height | int | The new height. |

**Returns**

| Type | Description |
| :- | :- |
| int | The proportional width. |


### get_proportional_height(width, height, new_width)  [static] {#get_proportional_height_width_height_new_width_57}


```
 get_proportional_height(width, height, new_width) 
```

Gets a proportional height.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| width | int | The width. |
| height | int | The height. |
| new_width | int | The new width. |

**Returns**

| Type | Description |
| :- | :- |
| int | The proportional height. |


### get_embedded_images() {#get_embedded_images__58}


```
 get_embedded_images() 
```

Gets the embedded images.

**Returns**

| Type | Description |
| :- | :- |
| [EmbeddedImage[]](/imaging/python-net/aspose.imaging/embeddedimage) | Array of images |


### get_used_fonts() {#get_used_fonts__59}


```
 get_used_fonts() 
```

Returns the list of font which used inside metafile.

**Returns**

| Type | Description |
| :- | :- |
| string | The font list |


### get_missed_fonts() {#get_missed_fonts__60}


```
 get_missed_fonts() 
```

Returns the list of fonts which used inside metafile but not found.

**Returns**

| Type | Description |
| :- | :- |
| string | The font list |


### resize_canvas(new_rectangle) {#resize_canvas_new_rectangle_61}


```
 resize_canvas(new_rectangle) 
```

Resizes the canvas.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_rectangle | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | The new rectangle. |

