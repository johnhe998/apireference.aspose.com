---
title: TextMeasurer
second_title: Aspose.BarCode for Java API Reference
description: Represents text measurer.
type: docs
weight: 57
url: /java/com.aspose.barcode.generation/textmeasurer/
---
**Inheritance:**
java.lang.Object

**All Implemented Interfaces:**
com.aspose.barcode.internal.ITextMeasurer
```
public class TextMeasurer implements ITextMeasurer
```

Represents text measurer. Full Framework implementation. TODO: Cache bitmap and graphics
## Constructors

| Constructor | Description |
| --- | --- |
| [TextMeasurer(float dpi, AntiAliasMode antiAliasMode)](#TextMeasurer-float-com.aspose.barcode.drawing.AntiAliasMode-) | Initializes new instance of class  TextMeasurer . |
## Methods

| Method | Description |
| --- | --- |
| [dispose()](#dispose--) | Disposes measurer and internal resources. |
| [equals(Object arg0)](#equals-java.lang.Object-) |  |
| [getClass()](#getClass--) |  |
| [hashCode()](#hashCode--) |  |
| [measureCharacterRanges(String text, System.Drawing.Font font, System.Drawing.RectangleF rectangle, TextOptions textOptions)](#measureCharacterRanges-java.lang.String-com.aspose.ms.System.Drawing.Font-com.aspose.ms.System.Drawing.RectangleF-com.aspose.barcode.drawing.TextOptions-) | Gets characters drawing Rectangles Resolution and AntiAlias Mode set in constructor |
| [measureString(String str, float width, System.Drawing.Font font)](#measureString-java.lang.String-float-com.aspose.ms.System.Drawing.Font-) | Measure string with specified width, font. |
| [notify()](#notify--) |  |
| [notifyAll()](#notifyAll--) |  |
| [offsetRectangle(System.Drawing.RectangleF nativeRectangle, boolean isNoWrap, VerticalTextAlignment verticalAlignment)](#offsetRectangle-com.aspose.ms.System.Drawing.RectangleF-boolean-com.aspose.barcode.drawing.VerticalTextAlignment-) |  |
| [reOffsetRectangle(System.Drawing.RectangleF symbolArea, System.Drawing.RectangleF nativeRectangle, System.Drawing.RectangleF offsetRectangle, HorizontalTextAlignment horisontalAlignment)](#reOffsetRectangle-com.aspose.ms.System.Drawing.RectangleF-com.aspose.ms.System.Drawing.RectangleF-com.aspose.ms.System.Drawing.RectangleF-com.aspose.barcode.drawing.HorizontalTextAlignment-) |  |
| [toString()](#toString--) |  |
| [wait()](#wait--) |  |
| [wait(long arg0)](#wait-long-) |  |
| [wait(long arg0, int arg1)](#wait-long-int-) |  |
### TextMeasurer(float dpi, AntiAliasMode antiAliasMode) {#TextMeasurer-float-com.aspose.barcode.drawing.AntiAliasMode-}
```
public TextMeasurer(float dpi, AntiAliasMode antiAliasMode)
```


Initializes new instance of class  TextMeasurer .

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| dpi | float | Dpi of target canvas |
| antiAliasMode | com.aspose.barcode.drawing.AntiAliasMode | Text antialising mode |

### dispose() {#dispose--}
```
public void dispose()
```


Disposes measurer and internal resources.

### equals(Object arg0) {#equals-java.lang.Object-}
```
public boolean equals(Object arg0)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| arg0 | java.lang.Object |  |

**Returns:**
boolean
### getClass() {#getClass--}
```
public final native Class<?> getClass()
```




**Returns:**
java.lang.Class<?>
### hashCode() {#hashCode--}
```
public native int hashCode()
```




**Returns:**
int
### measureCharacterRanges(String text, System.Drawing.Font font, System.Drawing.RectangleF rectangle, TextOptions textOptions) {#measureCharacterRanges-java.lang.String-com.aspose.ms.System.Drawing.Font-com.aspose.ms.System.Drawing.RectangleF-com.aspose.barcode.drawing.TextOptions-}
```
public System.Drawing.RectangleF[] measureCharacterRanges(String text, System.Drawing.Font font, System.Drawing.RectangleF rectangle, TextOptions textOptions)
```


Gets characters drawing Rectangles Resolution and AntiAlias Mode set in constructor

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | measuring text |
| font | com.aspose.ms.System.Drawing.Font | measuring font |
| rectangle | com.aspose.ms.System.Drawing.RectangleF | bounding rectangle |
| textOptions | com.aspose.barcode.drawing.TextOptions | text alignment |

**Returns:**
com.aspose.ms.System.Drawing.RectangleF[] - characters rectangles
### measureString(String str, float width, System.Drawing.Font font) {#measureString-java.lang.String-float-com.aspose.ms.System.Drawing.Font-}
```
public System.Drawing.SizeF measureString(String str, float width, System.Drawing.Font font)
```


Measure string with specified width, font. Resolution and AntiAlias Mode set in constructor

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| str | java.lang.String | A string |
| width | float | A width |
| font | com.aspose.ms.System.Drawing.Font | A font |

**Returns:**
com.aspose.ms.System.Drawing.SizeF - Size of a string
### notify() {#notify--}
```
public final native void notify()
```




### notifyAll() {#notifyAll--}
```
public final native void notifyAll()
```




### offsetRectangle(System.Drawing.RectangleF nativeRectangle, boolean isNoWrap, VerticalTextAlignment verticalAlignment) {#offsetRectangle-com.aspose.ms.System.Drawing.RectangleF-boolean-com.aspose.barcode.drawing.VerticalTextAlignment-}
```
public static System.Drawing.RectangleF offsetRectangle(System.Drawing.RectangleF nativeRectangle, boolean isNoWrap, VerticalTextAlignment verticalAlignment)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| nativeRectangle | com.aspose.ms.System.Drawing.RectangleF |  |
| isNoWrap | boolean |  |
| verticalAlignment | com.aspose.barcode.drawing.VerticalTextAlignment |  |

**Returns:**
com.aspose.ms.System.Drawing.RectangleF
### reOffsetRectangle(System.Drawing.RectangleF symbolArea, System.Drawing.RectangleF nativeRectangle, System.Drawing.RectangleF offsetRectangle, HorizontalTextAlignment horisontalAlignment) {#reOffsetRectangle-com.aspose.ms.System.Drawing.RectangleF-com.aspose.ms.System.Drawing.RectangleF-com.aspose.ms.System.Drawing.RectangleF-com.aspose.barcode.drawing.HorizontalTextAlignment-}
```
public static void reOffsetRectangle(System.Drawing.RectangleF symbolArea, System.Drawing.RectangleF nativeRectangle, System.Drawing.RectangleF offsetRectangle, HorizontalTextAlignment horisontalAlignment)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| symbolArea | com.aspose.ms.System.Drawing.RectangleF |  |
| nativeRectangle | com.aspose.ms.System.Drawing.RectangleF |  |
| offsetRectangle | com.aspose.ms.System.Drawing.RectangleF |  |
| horisontalAlignment | com.aspose.barcode.drawing.HorizontalTextAlignment |  |

### toString() {#toString--}
```
public String toString()
```




**Returns:**
java.lang.String
### wait() {#wait--}
```
public final void wait()
```




### wait(long arg0) {#wait-long-}
```
public final native void wait(long arg0)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| arg0 | long |  |

### wait(long arg0, int arg1) {#wait-long-int-}
```
public final void wait(long arg0, int arg1)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| arg0 | long |  |
| arg1 | int |  |

