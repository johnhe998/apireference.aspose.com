---
title: PsDocument
second_title: Aspose.Page for Java API Reference
description: This class encapsulates PS/EPS documents.
type: docs
weight: 16
url: /java/com.aspose.eps/psdocument/
---
**Inheritance:**
java.lang.Object, [com.aspose.page.Document](../../com.aspose.page/document)
```
public final class PsDocument extends Document
```

This class encapsulates PS/EPS documents.
## Constructors

| Constructor | Description |
| --- | --- |
| [PsDocument(OutputStream psStream, PsSaveOptions options)](#PsDocument-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-) | Initializes empty  PsDocument  with initialized page. |
| [PsDocument(OutputStream psStream, PsSaveOptions options, boolean multipaged)](#PsDocument-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-boolean-) | Initializes empty  PsDocument . |
| [PsDocument(OutputStream psStream, PsSaveOptions options, int numberOfPages)](#PsDocument-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-int-) | Initializes empty  PsDocument  when the number of Postscript document pages is known in advance. |
| [PsDocument(InputStream psStream)](#PsDocument-java.io.InputStream-) | Initializes  PsDocument  with a stream of PS/EPS file. |
| [PsDocument(InputStream psStream, LoadOptions loadOptions)](#PsDocument-java.io.InputStream-com.aspose.eps.LoadOptions-) | Initializes  PsDocument  with a stream and load options. |
## Methods

| Method | Description |
| --- | --- |
| [setInputStream(InputStream is)](#setInputStream-java.io.InputStream-) | Specifies an input stream. |
| [save(Device device, SaveOptions options)](#save-com.aspose.page.Device-com.aspose.page.SaveOptions-) | Saves PS/EPS file to a device. |
| [save(OutputStream epsStream)](#save-java.io.OutputStream-) | Saves given PsDocument as EPS file. |
| [save()](#save--) | Saves given PsDocument as PS file. |
| [getXmpMetadata()](#getXmpMetadata--) | Reads PS/EPS file and extracts XmpMetdata if it already exists or add new one if it doesn't exist. |
| [saveImageAsEps(InputStream imageStream, OutputStream epsStream, PsSaveOptions options)](#saveImageAsEps-java.io.InputStream-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-) | Saves PNG/JPEG/BMP/GIF image from input stream to EPS output stream. |
| [saveImageAsEps(String imageFilePath, String epsFilePath, PsSaveOptions options)](#saveImageAsEps-java.lang.String-java.lang.String-com.aspose.eps.device.PsSaveOptions-) | Saves PNG/JPEG/BMP/GIF image from file to EPS file. |
| [saveImageAsEps(BufferedImage image, String epsFilePath, PsSaveOptions options)](#saveImageAsEps-java.awt.image.BufferedImage-java.lang.String-com.aspose.eps.device.PsSaveOptions-) | Saves BufferedImage object to EPS file. |
| [saveImageAsEps(BufferedImage image, OutputStream epsStream, PsSaveOptions options)](#saveImageAsEps-java.awt.image.BufferedImage-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-) | Saves BufferedImage object to EPS file. |
| [setPageSize(float width, float height)](#setPageSize-float-float-) | Sets page size. |
| [setPageDevice(Map<String,Object> pageParams)](#setPageDevice-java.util.Map-java.lang.String-java.lang.Object--) | Sets page device parameters (see operator "setpagedevice" PostScript spesification). |
| [openPage(float width, float height)](#openPage-float-float-) | Creates new page and make it current one. |
| [openPage(String pageName)](#openPage-java.lang.String-) | Creates new page with document's size and make it current one. |
| [closePage()](#closePage--) | Complete current page. |
| [writeGraphicsSave()](#writeGraphicsSave--) | Writes saving of the current graphics state (see PostScript specification on operator "gsave"). |
| [writeGraphicsRestore()](#writeGraphicsRestore--) | Writes restoring of the current graphics state (see PostScript specification on operator "grestore"). |
| [setTransform(AffineTransform matrix)](#setTransform-java.awt.geom.AffineTransform-) | Set current transformation to this one. |
| [transform(AffineTransform matrix)](#transform-java.awt.geom.AffineTransform-) | Adds transformation to current graphics state (concatenates this matrix with current one). |
| [translate(float x, float y)](#translate-float-float-) | Adds translation to current graphics state (translates current matrix). |
| [scale(float xScale, float yScale)](#scale-float-float-) | Adds scale to current graphics state (scale current matrix). |
| [rotate(float angleRadians)](#rotate-float-) | Adds rotation counterclockwise about the origin to current graphics state (rotate current matrix). |
| [rotate(int angleDegrees)](#rotate-int-) | Adds rotation counterclockwise about the origin to current graphics state (rotate current matrix). |
| [shear(float shx, float shy)](#shear-float-float-) | Adds shear transformation to current graphics state (shear current matrix). |
| [clip(Shape s)](#clip-java.awt.Shape-) | Adds clip to current graphics state. |
| [clipText(String text, Font font, float x, float y)](#clipText-java.lang.String-java.awt.Font-float-float-) | Adds clip from an outline of given text in given font. |
| [clipRectangle(Rectangle2D.Float rect)](#clipRectangle-java.awt.geom.Rectangle2D.Float-) | Adds clipping rectangle to current graphics state. |
| [clipAndNewPath(Shape s)](#clipAndNewPath-java.awt.Shape-) | Adds clip to current graphics state and than writes "newpath" operator. |
| [setPaint(Paint paint)](#setPaint-java.awt.Paint-) | Sets paint in current graphics state. |
| [getPaint()](#getPaint--) | Gets paint in current graphics state. |
| [setStroke(Stroke stroke)](#setStroke-java.awt.Stroke-) | Sets stroke in current graphics state. |
| [getStroke()](#getStroke--) | Gets stroke in current graphics state. |
| [fillText(String text, Font font, float x, float y)](#fillText-java.lang.String-java.awt.Font-float-float-) | Adds a text string by filling interior of glyphs. |
| [fillText(String text, float[] advances, Font font, float x, float y)](#fillText-java.lang.String-float---java.awt.Font-float-float-) | Adds a text string by filling interior of glyphs. |
| [fillText(String text, DrFont drFont, float x, float y)](#fillText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-) | Adds a text string by filling interior of glyphs. |
| [fillText(String text, float[] advances, DrFont drFont, float x, float y)](#fillText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-) | Adds a text string by filling interior of glyphs. |
| [fillText(String text, Font font, float x, float y, Paint fill)](#fillText-java.lang.String-java.awt.Font-float-float-java.awt.Paint-) | Adds a text string by filling interior of glyphs. |
| [fillText(String text, float[] advances, Font font, float x, float y, Paint fill)](#fillText-java.lang.String-float---java.awt.Font-float-float-java.awt.Paint-) | Adds a text string by filling interior of glyphs. |
| [fillText(String text, DrFont drFont, float x, float y, Paint fill)](#fillText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-) | Adds a text string by filling interior of glyphs. |
| [fillText(String text, float[] advances, DrFont drFont, float x, float y, Paint fill)](#fillText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-) | Adds a text string by filling interior of glyphs. |
| [outlineText(String text, Font font, float x, float y)](#outlineText-java.lang.String-java.awt.Font-float-float-) | Adds a text string by drawing glyphs contours. |
| [outlineText(String text, float[] advances, Font font, float x, float y)](#outlineText-java.lang.String-float---java.awt.Font-float-float-) | Adds a text string by drawing glyphs contours. |
| [outlineText(String text, DrFont drFont, float x, float y)](#outlineText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-) | Adds a text string by drawing glyphs contours. |
| [outlineText(String text, float[] advances, DrFont drFont, float x, float y)](#outlineText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-) | Adds a text string by drawing glyphs contours. |
| [outlineText(String text, Font font, float x, float y, Paint outlinePaint, Stroke stroke)](#outlineText-java.lang.String-java.awt.Font-float-float-java.awt.Paint-java.awt.Stroke-) | Adds a text string by drawing glyphs contours. |
| [outlineText(String text, float[] advances, Font font, float x, float y, Paint outlinePaint, Stroke stroke)](#outlineText-java.lang.String-float---java.awt.Font-float-float-java.awt.Paint-java.awt.Stroke-) | Adds a text string by drawing glyphs contours. |
| [outlineText(String text, DrFont drFont, float x, float y, Paint outlinePaint, Stroke stroke)](#outlineText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-java.awt.Stroke-) | Adds a text string by drawing glyphs contours. |
| [outlineText(String text, float[] advances, DrFont drFont, float x, float y, Paint outlinePaint, Stroke stroke)](#outlineText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-java.awt.Stroke-) | Adds a text string by drawing glyphs contours. |
| [fillAndStrokeText(String text, Font font, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke)](#fillAndStrokeText-java.lang.String-java.awt.Font-float-float-java.awt.Paint-java.awt.Paint-java.awt.Stroke-) | Adds a text string by filling interior of glyphs and drawing glyphs contours. |
| [fillAndStrokeText(String text, float[] advances, Font font, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke)](#fillAndStrokeText-java.lang.String-float---java.awt.Font-float-float-java.awt.Paint-java.awt.Paint-java.awt.Stroke-) | Adds a text string by filling interior of glyphs and drawing glyphs contours. |
| [fillAndStrokeText(String text, DrFont drFont, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke)](#fillAndStrokeText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-java.awt.Paint-java.awt.Stroke-) | Adds a text string by filling interior of glyphs and drawing glyphs contours. |
| [fillAndStrokeText(String text, float[] advances, DrFont drFont, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke)](#fillAndStrokeText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-java.awt.Paint-java.awt.Stroke-) | Adds a text string by filling interior of glyphs and drawing glyphs contours. |
| [fill(Shape shape)](#fill-java.awt.Shape-) | Fill an arbitrary path. |
| [draw(Shape shape)](#draw-java.awt.Shape-) | Draw an arbitrary path. |
| [drawImage(BufferedImage image)](#drawImage-java.awt.image.BufferedImage-) | Draw an image. |
| [drawImage(BufferedImage image, AffineTransform transform, Color bkg)](#drawImage-java.awt.image.BufferedImage-java.awt.geom.AffineTransform-java.awt.Color-) | Draw transformed image with background. |
| [drawTransparentImage(BufferedImage image, AffineTransform transform, int transparencyThreshold)](#drawTransparentImage-java.awt.image.BufferedImage-java.awt.geom.AffineTransform-int-) | Draw transformed transparent image with background. |
| [drawExplicitImageMask(BufferedImage image24bpp, BufferedImage alphaMask1bpp, AffineTransform transform)](#drawExplicitImageMask-java.awt.image.BufferedImage-java.awt.image.BufferedImage-java.awt.geom.AffineTransform-) | Draw masked image. |
| [getNumberOfPages()](#getNumberOfPages--) | Gets a quantity of pages in resulting PDF document. |
| [merge(String[] filesForMerge, Device device, SaveOptions options)](#merge-java.lang.String---com.aspose.page.Device-com.aspose.page.SaveOptions-) | Merges PS/EPS files to a device. |
### PsDocument(OutputStream psStream, PsSaveOptions options) {#PsDocument-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-}
```
public PsDocument(OutputStream psStream, PsSaveOptions options)
```


Initializes empty  PsDocument  with initialized page.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| psStream | java.io.OutputStream | Stream where to save PS/EPS file. |
| options | [PsSaveOptions](../../com.aspose.eps.device/pssaveoptions) | A set of parameters controlling saving of PostScript file. |

### PsDocument(OutputStream psStream, PsSaveOptions options, boolean multipaged) {#PsDocument-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-boolean-}
```
public PsDocument(OutputStream psStream, PsSaveOptions options, boolean multipaged)
```


Initializes empty  PsDocument .

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| psStream | java.io.OutputStream | Stream where to save PS/EPS file. |
| options | [PsSaveOptions](../../com.aspose.eps.device/pssaveoptions) | A set of parameters controlling saving of PostScript file. |
| multipaged | boolean | If false page will not be initialized. In this case page initialization should be performed via explicit "openPage(width, height) call." |

### PsDocument(OutputStream psStream, PsSaveOptions options, int numberOfPages) {#PsDocument-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-int-}
```
public PsDocument(OutputStream psStream, PsSaveOptions options, int numberOfPages)
```


Initializes empty  PsDocument  when the number of Postscript document pages is known in advance.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| psStream | java.io.OutputStream | Stream where to save PS/EPS file. |
| options | [PsSaveOptions](../../com.aspose.eps.device/pssaveoptions) | A set of parameters controlling saving of PostScript file. |
| numberOfPages | int | The number of pages in the PostScript document. |

### PsDocument(InputStream psStream) {#PsDocument-java.io.InputStream-}
```
public PsDocument(InputStream psStream)
```


Initializes  PsDocument  with a stream of PS/EPS file.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| psStream | java.io.InputStream | Stream of PS/EPS file. |

### PsDocument(InputStream psStream, LoadOptions loadOptions) {#PsDocument-java.io.InputStream-com.aspose.eps.LoadOptions-}
```
public PsDocument(InputStream psStream, LoadOptions loadOptions)
```


Initializes  PsDocument  with a stream and load options.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| psStream | java.io.InputStream | Stream of PS/EPS file. |
| loadOptions | [LoadOptions](../../com.aspose.eps/loadoptions) | Set of parameters controlling loading of PS file. |

### setInputStream(InputStream is) {#setInputStream-java.io.InputStream-}
```
public void setInputStream(InputStream is)
```


Specifies an input stream.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| is | java.io.InputStream | Input stream of PS/EPS file. |

### save(Device device, SaveOptions options) {#save-com.aspose.page.Device-com.aspose.page.SaveOptions-}
```
public void save(Device device, SaveOptions options)
```


Saves PS/EPS file to a device.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| device | [Device](../../com.aspose.page/device) | An output device. |
| options | [SaveOptions](../../com.aspose.page/saveoptions) | Contains flags that specify output of errors thrown during conversion. |

### save(OutputStream epsStream) {#save-java.io.OutputStream-}
```
public void save(OutputStream epsStream)
```


Saves given PsDocument as EPS file. This method is used only after updating XMP metadata. It saves initial EPS file with updated existing metadata or new one created while calling getMetadata method. In the last case all necessary PostScript code and EPS comments are added.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| epsStream | java.io.OutputStream | Stream of output EPS file. |

### save() {#save--}
```
public void save()
```


Saves given PsDocument as PS file. This method is used only when PsDocument was created from scratch.

### getXmpMetadata() {#getXmpMetadata--}
```
public XmpMetadata getXmpMetadata()
```


Reads PS/EPS file and extracts XmpMetdata if it already exists or add new one if it doesn't exist.

**Returns:**
[XmpMetadata](../../com.aspose.eps.xmp/xmpmetadata) - existing or new instance of XMP metadata.
### saveImageAsEps(InputStream imageStream, OutputStream epsStream, PsSaveOptions options) {#saveImageAsEps-java.io.InputStream-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-}
```
public static void saveImageAsEps(InputStream imageStream, OutputStream epsStream, PsSaveOptions options)
```


Saves PNG/JPEG/BMP/GIF image from input stream to EPS output stream.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| imageStream | java.io.InputStream | Image input stream. |
| epsStream | java.io.OutputStream | EPS output stream. |
| options | [PsSaveOptions](../../com.aspose.eps.device/pssaveoptions) | Contains parameters that specify output of errors thrown during conversion. |

### saveImageAsEps(String imageFilePath, String epsFilePath, PsSaveOptions options) {#saveImageAsEps-java.lang.String-java.lang.String-com.aspose.eps.device.PsSaveOptions-}
```
public static void saveImageAsEps(String imageFilePath, String epsFilePath, PsSaveOptions options)
```


Saves PNG/JPEG/BMP/GIF image from file to EPS file.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| imageFilePath | java.lang.String | Image file path. |
| epsFilePath | java.lang.String | EPS file path. |
| options | [PsSaveOptions](../../com.aspose.eps.device/pssaveoptions) | Contains parameters that specify output of errors thrown during conversion. |

### saveImageAsEps(BufferedImage image, String epsFilePath, PsSaveOptions options) {#saveImageAsEps-java.awt.image.BufferedImage-java.lang.String-com.aspose.eps.device.PsSaveOptions-}
```
public static void saveImageAsEps(BufferedImage image, String epsFilePath, PsSaveOptions options)
```


Saves BufferedImage object to EPS file.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| image | java.awt.image.BufferedImage | The Image. |
| epsFilePath | java.lang.String | EPS file path. |
| options | [PsSaveOptions](../../com.aspose.eps.device/pssaveoptions) | Contains parameters that specify output of errors thrown during conversion. |

### saveImageAsEps(BufferedImage image, OutputStream epsStream, PsSaveOptions options) {#saveImageAsEps-java.awt.image.BufferedImage-java.io.OutputStream-com.aspose.eps.device.PsSaveOptions-}
```
public static void saveImageAsEps(BufferedImage image, OutputStream epsStream, PsSaveOptions options)
```


Saves BufferedImage object to EPS file.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| image | java.awt.image.BufferedImage | The Image. |
| epsStream | java.io.OutputStream | EPS output stream. |
| options | [PsSaveOptions](../../com.aspose.eps.device/pssaveoptions) | Contains parameters that specify output of errors thrown during conversion. |

### setPageSize(float width, float height) {#setPageSize-float-float-}
```
public void setPageSize(float width, float height)
```


Sets page size. To create pages with different sizes in one document use  setPageDevice  method just after this method.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| width | float | The width of page in resulting PostScript file. |
| height | float | The height of page in resulting PostScript file. |

### setPageDevice(Map<String,Object> pageParams) {#setPageDevice-java.util.Map-java.lang.String-java.lang.Object--}
```
public void setPageDevice(Map<String,Object> pageParams)
```


Sets page device parameters (see operator "setpagedevice" PostScript spesification). Among these can be page size and color etc.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| pageParams | java.util.Map<java.lang.String,java.lang.Object> | Parameters of the page. In this dictionary can be page size and color etc. |

### openPage(float width, float height) {#openPage-float-float-}
```
public void openPage(float width, float height)
```


Creates new page and make it current one.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| width | float | The width of new page. |
| height | float | The height of new page. |

### openPage(String pageName) {#openPage-java.lang.String-}
```
public void openPage(String pageName)
```


Creates new page with document's size and make it current one.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| pageName | java.lang.String | The name of new page. If it is null the name o the page will be an order number of the page. |

### closePage() {#closePage--}
```
public void closePage()
```


Complete current page.

### writeGraphicsSave() {#writeGraphicsSave--}
```
public void writeGraphicsSave()
```


Writes saving of the current graphics state (see PostScript specification on operator "gsave").

### writeGraphicsRestore() {#writeGraphicsRestore--}
```
public void writeGraphicsRestore()
```


Writes restoring of the current graphics state (see PostScript specification on operator "grestore").

### setTransform(AffineTransform matrix) {#setTransform-java.awt.geom.AffineTransform-}
```
public void setTransform(AffineTransform matrix)
```


Set current transformation to this one.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| matrix | java.awt.geom.AffineTransform | The transformation. |

### transform(AffineTransform matrix) {#transform-java.awt.geom.AffineTransform-}
```
public void transform(AffineTransform matrix)
```


Adds transformation to current graphics state (concatenates this matrix with current one).

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| matrix | java.awt.geom.AffineTransform | The transformation. |

### translate(float x, float y) {#translate-float-float-}
```
public void translate(float x, float y)
```


Adds translation to current graphics state (translates current matrix).

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| x | float | The translation in X direction. |
| y | float | The translation in Y direction. |

### scale(float xScale, float yScale) {#scale-float-float-}
```
public void scale(float xScale, float yScale)
```


Adds scale to current graphics state (scale current matrix).

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| xScale | float | The scale in X axis. |
| yScale | float | The scale in Y axis. |

### rotate(float angleRadians) {#rotate-float-}
```
public void rotate(float angleRadians)
```


Adds rotation counterclockwise about the origin to current graphics state (rotate current matrix).

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| angleRadians | float | The angle of rotation in radians. |

### rotate(int angleDegrees) {#rotate-int-}
```
public void rotate(int angleDegrees)
```


Adds rotation counterclockwise about the origin to current graphics state (rotate current matrix).

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| angleDegrees | int | The angle of rotation in degrees. |

### shear(float shx, float shy) {#shear-float-float-}
```
public void shear(float shx, float shy)
```


Adds shear transformation to current graphics state (shear current matrix).

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| shx | float | The shear in X axis. |
| shy | float | The shear in Y axis. |

### clip(Shape s) {#clip-java.awt.Shape-}
```
public void clip(Shape s)
```


Adds clip to current graphics state.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| s | java.awt.Shape | The clipping path. |

### clipText(String text, Font font, float x, float y) {#clipText-java.lang.String-java.awt.Font-float-float-}
```
public void clipText(String text, Font font, float x, float y)
```


Adds clip from an outline of given text in given font.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text. |
| font | java.awt.Font | The font. |
| x | float | An X coordinate of the text position. |
| y | float |  |

### clipRectangle(Rectangle2D.Float rect) {#clipRectangle-java.awt.geom.Rectangle2D.Float-}
```
public void clipRectangle(Rectangle2D.Float rect)
```


Adds clipping rectangle to current graphics state.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| rect | java.awt.geom.Rectangle2D.Float | The clipping rectangle. |

### clipAndNewPath(Shape s) {#clipAndNewPath-java.awt.Shape-}
```
public void clipAndNewPath(Shape s)
```


Adds clip to current graphics state and than writes "newpath" operator. It is necessary to do to escape of confluence of this clipping path and some subsequent pathes such as glyphs outlined with "charpath" operator.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| s | java.awt.Shape | The clipping path. |

### setPaint(Paint paint) {#setPaint-java.awt.Paint-}
```
public void setPaint(Paint paint)
```


Sets paint in current graphics state.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| paint | java.awt.Paint | The paint. It can be any subclass of  Paint  class existed in JDK. |

### getPaint() {#getPaint--}
```
public Paint getPaint()
```


Gets paint in current graphics state.

**Returns:**
java.awt.Paint - Current paint.
### setStroke(Stroke stroke) {#setStroke-java.awt.Stroke-}
```
public void setStroke(Stroke stroke)
```


Sets stroke in current graphics state.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| stroke | java.awt.Stroke | The stroke. |

### getStroke() {#getStroke--}
```
public Stroke getStroke()
```


Gets stroke in current graphics state.

**Returns:**
java.awt.Stroke - Current stroke.
### fillText(String text, Font font, float x, float y) {#fillText-java.lang.String-java.awt.Font-float-float-}
```
public void fillText(String text, Font font, float x, float y)
```


Adds a text string by filling interior of glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| font | java.awt.Font | System font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |

### fillText(String text, float[] advances, Font font, float x, float y) {#fillText-java.lang.String-float---java.awt.Font-float-float-}
```
public void fillText(String text, float[] advances, Font font, float x, float y)
```


Adds a text string by filling interior of glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| advances | float[] | An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| font | java.awt.Font | System font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |

### fillText(String text, DrFont drFont, float x, float y) {#fillText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-}
```
public void fillText(String text, DrFont drFont, float x, float y)
```


Adds a text string by filling interior of glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |

### fillText(String text, float[] advances, DrFont drFont, float x, float y) {#fillText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-}
```
public void fillText(String text, float[] advances, DrFont drFont, float x, float y)
```


Adds a text string by filling interior of glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| advances | float[] | An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |

### fillText(String text, Font font, float x, float y, Paint fill) {#fillText-java.lang.String-java.awt.Font-float-float-java.awt.Paint-}
```
public void fillText(String text, Font font, float x, float y, Paint fill)
```


Adds a text string by filling interior of glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| font | java.awt.Font | The font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| fill | java.awt.Paint | The fill used for painting glyphs. |

### fillText(String text, float[] advances, Font font, float x, float y, Paint fill) {#fillText-java.lang.String-float---java.awt.Font-float-float-java.awt.Paint-}
```
public void fillText(String text, float[] advances, Font font, float x, float y, Paint fill)
```


Adds a text string by filling interior of glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| advances | float[] | An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| font | java.awt.Font | The font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| fill | java.awt.Paint | The fill used for painting glyphs. |

### fillText(String text, DrFont drFont, float x, float y, Paint fill) {#fillText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-}
```
public void fillText(String text, DrFont drFont, float x, float y, Paint fill)
```


Adds a text string by filling interior of glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| fill | java.awt.Paint | The fill used for painting glyphs. |

### fillText(String text, float[] advances, DrFont drFont, float x, float y, Paint fill) {#fillText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-}
```
public void fillText(String text, float[] advances, DrFont drFont, float x, float y, Paint fill)
```


Adds a text string by filling interior of glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| advances | float[] | An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| fill | java.awt.Paint | The fill used for painting glyphs. |

### outlineText(String text, Font font, float x, float y) {#outlineText-java.lang.String-java.awt.Font-float-float-}
```
public void outlineText(String text, Font font, float x, float y)
```


Adds a text string by drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| font | java.awt.Font | System font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |

### outlineText(String text, float[] advances, Font font, float x, float y) {#outlineText-java.lang.String-float---java.awt.Font-float-float-}
```
public void outlineText(String text, float[] advances, Font font, float x, float y)
```


Adds a text string by drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| advances | float[] | An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| font | java.awt.Font | System font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |

### outlineText(String text, DrFont drFont, float x, float y) {#outlineText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-}
```
public void outlineText(String text, DrFont drFont, float x, float y)
```


Adds a text string by drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |

### outlineText(String text, float[] advances, DrFont drFont, float x, float y) {#outlineText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-}
```
public void outlineText(String text, float[] advances, DrFont drFont, float x, float y)
```


Adds a text string by drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| advances | float[] | An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |

### outlineText(String text, Font font, float x, float y, Paint outlinePaint, Stroke stroke) {#outlineText-java.lang.String-java.awt.Font-float-float-java.awt.Paint-java.awt.Stroke-}
```
public void outlineText(String text, Font font, float x, float y, Paint outlinePaint, Stroke stroke)
```


Adds a text string by drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| font | java.awt.Font | The font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| outlinePaint | java.awt.Paint | The  java.awt.Paint  used for painting glyphs outlines. Can be any subclass of  java.awt.Paint  class in JDK. |
| stroke | java.awt.Stroke | The stroke used for drawing glyphs contours. |

### outlineText(String text, float[] advances, Font font, float x, float y, Paint outlinePaint, Stroke stroke) {#outlineText-java.lang.String-float---java.awt.Font-float-float-java.awt.Paint-java.awt.Stroke-}
```
public void outlineText(String text, float[] advances, Font font, float x, float y, Paint outlinePaint, Stroke stroke)
```


Adds a text string by drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| advances | float[] | An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| font | java.awt.Font | The font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| outlinePaint | java.awt.Paint | The  java.awt.Paint  used for painting glyphs outlines. Can be any subclass of  java.awt.Paint  class in JDK. |
| stroke | java.awt.Stroke | The stroke used for drawing glyphs contours. |

### outlineText(String text, DrFont drFont, float x, float y, Paint outlinePaint, Stroke stroke) {#outlineText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-java.awt.Stroke-}
```
public void outlineText(String text, DrFont drFont, float x, float y, Paint outlinePaint, Stroke stroke)
```


Adds a text string by drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| outlinePaint | java.awt.Paint | The  java.awt.Paint  used for painting glyphs outlines. Can be any subclass of  java.awt.Paint  class in JDK. |
| stroke | java.awt.Stroke | The stroke used for drawing glyphs contours. |

### outlineText(String text, float[] advances, DrFont drFont, float x, float y, Paint outlinePaint, Stroke stroke) {#outlineText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-java.awt.Stroke-}
```
public void outlineText(String text, float[] advances, DrFont drFont, float x, float y, Paint outlinePaint, Stroke stroke)
```


Adds a text string by drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| advances | float[] | An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| outlinePaint | java.awt.Paint | The  java.awt.Paint  used for painting glyphs outlines. Can be any subclass of  java.awt.Paint  class in JDK. |
| stroke | java.awt.Stroke | The stroke used for drawing glyphs contours. |

### fillAndStrokeText(String text, Font font, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke) {#fillAndStrokeText-java.lang.String-java.awt.Font-float-float-java.awt.Paint-java.awt.Paint-java.awt.Stroke-}
```
public void fillAndStrokeText(String text, Font font, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke)
```


Adds a text string by filling interior of glyphs and drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| font | java.awt.Font | System font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| fillPaint | java.awt.Paint | The fill used for painting glyphs interior. |
| strokePaint | java.awt.Paint | The  java.awt.Paint  used for painting glyphs outlines. Can be any subclass of  java.awt.Paint  class in JDK. |
| stroke | java.awt.Stroke | The stroke used for drawing glyphs contours. |

### fillAndStrokeText(String text, float[] advances, Font font, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke) {#fillAndStrokeText-java.lang.String-float---java.awt.Font-float-float-java.awt.Paint-java.awt.Paint-java.awt.Stroke-}
```
public void fillAndStrokeText(String text, float[] advances, Font font, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke)
```


Adds a text string by filling interior of glyphs and drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. advances An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| advances | float[] |  |
| font | java.awt.Font | System font that will be used to draw text. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| fillPaint | java.awt.Paint | The fill used for painting glyphs interior. |
| strokePaint | java.awt.Paint | The  java.awt.Paint  used for painting glyphs outlines. Can be any subclass of  java.awt.Paint  class in JDK. |
| stroke | java.awt.Stroke | The stroke used for drawing glyphs contours. |

### fillAndStrokeText(String text, DrFont drFont, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke) {#fillAndStrokeText-java.lang.String-com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-java.awt.Paint-java.awt.Stroke-}
```
public void fillAndStrokeText(String text, DrFont drFont, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke)
```


Adds a text string by filling interior of glyphs and drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| fillPaint | java.awt.Paint | The fill used for painting glyphs interior. |
| strokePaint | java.awt.Paint | The  java.awt.Paint  used for painting glyphs outlines. Can be any subclass of  java.awt.Paint  class in JDK. |
| stroke | java.awt.Stroke | The stroke used for drawing glyphs contours. |

### fillAndStrokeText(String text, float[] advances, DrFont drFont, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke) {#fillAndStrokeText-java.lang.String-float---com.aspose.foundation.drawing.DrFont-float-float-java.awt.Paint-java.awt.Paint-java.awt.Stroke-}
```
public void fillAndStrokeText(String text, float[] advances, DrFont drFont, float x, float y, Paint fillPaint, Paint strokePaint, Stroke stroke)
```


Adds a text string by filling interior of glyphs and drawing glyphs contours.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| text | java.lang.String | The text to add. |
| advances | float[] | An array of glyphs width. It's length must comply with the number of glyphs in the string. |
| drFont | com.aspose.foundation.drawing.DrFont |  DrFont  that will be used to draw text. It can be used with custom font that is located in custom folder. |
| x | float | X coordinate for text origin. |
| y | float | Y coordinate for text origin. |
| fillPaint | java.awt.Paint | The fill used for painting glyphs interior. |
| strokePaint | java.awt.Paint | The  java.awt.Paint  used for painting glyphs outlines. Can be any subclass of  java.awt.Paint  class in JDK. |
| stroke | java.awt.Stroke | The stroke used for drawing glyphs contours. |

### fill(Shape shape) {#fill-java.awt.Shape-}
```
public void fill(Shape shape)
```


Fill an arbitrary path.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| shape | java.awt.Shape | The path to fill. |

### draw(Shape shape) {#draw-java.awt.Shape-}
```
public void draw(Shape shape)
```


Draw an arbitrary path.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| shape | java.awt.Shape | The path to fill. |

### drawImage(BufferedImage image) {#drawImage-java.awt.image.BufferedImage-}
```
public void drawImage(BufferedImage image)
```


Draw an image.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| image | java.awt.image.BufferedImage | The image to draw. |

### drawImage(BufferedImage image, AffineTransform transform, Color bkg) {#drawImage-java.awt.image.BufferedImage-java.awt.geom.AffineTransform-java.awt.Color-}
```
public void drawImage(BufferedImage image, AffineTransform transform, Color bkg)
```


Draw transformed image with background.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| image | java.awt.image.BufferedImage | The image to draw. |
| transform | java.awt.geom.AffineTransform | The matrix to transform image. |
| bkg | java.awt.Color | The background for the image. |

### drawTransparentImage(BufferedImage image, AffineTransform transform, int transparencyThreshold) {#drawTransparentImage-java.awt.image.BufferedImage-java.awt.geom.AffineTransform-int-}
```
public void drawTransparentImage(BufferedImage image, AffineTransform transform, int transparencyThreshold)
```


Draw transformed transparent image with background. If image doesn't have Alpha channel it will be drawn as opaque image.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| image | java.awt.image.BufferedImage | The image to draw. |
| transform | java.awt.geom.AffineTransform | The matrix to transform image. |
| transparencyThreshold | int | A threshold that defines from which value of transparency pixel will be interpreted as fully transparent. All values below this threshold will be interpreted as fully opaque. |

### drawExplicitImageMask(BufferedImage image24bpp, BufferedImage alphaMask1bpp, AffineTransform transform) {#drawExplicitImageMask-java.awt.image.BufferedImage-java.awt.image.BufferedImage-java.awt.geom.AffineTransform-}
```
public void drawExplicitImageMask(BufferedImage image24bpp, BufferedImage alphaMask1bpp, AffineTransform transform)
```


Draw masked image.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| image24bpp | java.awt.image.BufferedImage | The image to draw. Must be in 24bpp RGB image format |
| alphaMask1bpp | java.awt.image.BufferedImage | The image mask. Must be in 1bpp image format. |
| transform | java.awt.geom.AffineTransform | The matrix to transform image. |

### getNumberOfPages() {#getNumberOfPages--}
```
public int getNumberOfPages()
```


Gets a quantity of pages in resulting PDF document.

**Returns:**
int - the number of pages.
### merge(String[] filesForMerge, Device device, SaveOptions options) {#merge-java.lang.String---com.aspose.page.Device-com.aspose.page.SaveOptions-}
```
public void merge(String[] filesForMerge, Device device, SaveOptions options)
```


Merges PS/EPS files to a device.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| filesForMerge | java.lang.String[] | PS/EPS files for merging with this file to an output device. |
| device | [Device](../../com.aspose.page/device) | An output device. |
| options | [SaveOptions](../../com.aspose.page/saveoptions) | Contains flags that specify output of errors thrown during conversion. |

