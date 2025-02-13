---
title: Type1Font
second_title: Aspose.Font for Java API Reference
description: Represents Type1 Font.
type: docs
weight: 93
url: /java/com.aspose.font/type1font/
---
**Inheritance:**
java.lang.Object, [com.aspose.font.Font](../../com.aspose.font/font)
```
public class Type1Font extends Font
```

Represents Type1 Font.
## Methods

| Method | Description |
| --- | --- |
| [getFontType()](#getFontType--) | Gets Font type. |
| [getFontFamily()](#getFontFamily--) | Gets Font family. |
| [setFontFamily(String value)](#setFontFamily-java.lang.String-) | The Font family setter is not implemented yet. |
| [getFontName()](#getFontName--) | Gets Font face name. |
| [setFontName(String value)](#setFontName-java.lang.String-) | The Font face name setter is not implemented yet. |
| [getFontNames()](#getFontNames--) | Gets Font names. |
| [getPostscriptNames()](#getPostscriptNames--) | Gets postscript Font names. |
| [getStyle()](#getStyle--) | Gets Font style. |
| [setStyle(String value)](#setStyle-java.lang.String-) | The Style setter is not implemented yet. |
| [getFontStyle()](#getFontStyle--) | Gets Font style. |
| [getNumGlyphs()](#getNumGlyphs--) | Gets number of glyphs in the Font. |
| [getMetrics()](#getMetrics--) | Gets Font metrics. |
| [getEncoding()](#getEncoding--) | Gets Font encoding. |
| [getGlyphById(String id)](#getGlyphById-java.lang.String-) | Returns glyph by glyph id. |
| [getGlyphById(long id)](#getGlyphById-long-) | Returns glyph by glyph id. |
| [getGlyphById(GlyphId id)](#getGlyphById-com.aspose.font.GlyphId-) | Returns glyph by glyph id. |
| [getAllGlyphIds()](#getAllGlyphIds--) | Returns array of all glyph ids, available in the Font. |
| [getGlyphIdType()](#getGlyphIdType--) | Glyph id type specification. |
| [getFontDefinition()](#getFontDefinition--) | Gets Font definition. |
| [convert(FontType fontType)](#convert-com.aspose.font.FontType-) | Converts the Font into another format. |
### getFontType() {#getFontType--}
```
public FontType getFontType()
```


Gets Font type. Returns FontType.Type1 value.

**Returns:**
[FontType](../../com.aspose.font/fonttype) - Font type.
### getFontFamily() {#getFontFamily--}
```
public String getFontFamily()
```


Gets Font family.

**Returns:**
java.lang.String - Font family.
### setFontFamily(String value) {#setFontFamily-java.lang.String-}
```
public void setFontFamily(String value)
```


The Font family setter is not implemented yet.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| value | java.lang.String | New Font family. |

### getFontName() {#getFontName--}
```
public String getFontName()
```


Gets Font face name.

**Returns:**
java.lang.String - Font face name.
### setFontName(String value) {#setFontName-java.lang.String-}
```
public void setFontName(String value)
```


The Font face name setter is not implemented yet.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| value | java.lang.String | New Font face name. |

### getFontNames() {#getFontNames--}
```
public MultiLanguageString getFontNames()
```


Gets Font names.

**Returns:**
[MultiLanguageString](../../com.aspose.font/multilanguagestring) - Font names.
### getPostscriptNames() {#getPostscriptNames--}
```
public MultiLanguageString getPostscriptNames()
```


Gets postscript Font names.

**Returns:**
[MultiLanguageString](../../com.aspose.font/multilanguagestring) - Postscript Font names
### getStyle() {#getStyle--}
```
public String getStyle()
```


Gets Font style. This is a raw string value provided by Font file.

**Returns:**
java.lang.String - Font style.
### setStyle(String value) {#setStyle-java.lang.String-}
```
public void setStyle(String value)
```


The Style setter is not implemented yet. This is a raw string value provided by Font file.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| value | java.lang.String | New Font style. |

### getFontStyle() {#getFontStyle--}
```
public int getFontStyle()
```


Gets Font style. This is a value computed and represented in generalized type.

**Returns:**
int - Font style. Usually, a combination of FontStyle class constant flag values or 0.
### getNumGlyphs() {#getNumGlyphs--}
```
public int getNumGlyphs()
```


Gets number of glyphs in the Font.

**Returns:**
int - Number of glyphs in the Font.
### getMetrics() {#getMetrics--}
```
public IFontMetrics getMetrics()
```


Gets Font metrics.

**Returns:**
[IFontMetrics](../../com.aspose.font/ifontmetrics) - Font metrics.
### getEncoding() {#getEncoding--}
```
public IFontEncoding getEncoding()
```


Gets Font encoding.

**Returns:**
[IFontEncoding](../../com.aspose.font/ifontencoding) - Font encoding.
### getGlyphById(String id) {#getGlyphById-java.lang.String-}
```
public Glyph getGlyphById(String id)
```


Returns glyph by glyph id.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| id | java.lang.String | Glyph id. |

**Returns:**
[Glyph](../../com.aspose.font/glyph) - Glyph.
### getGlyphById(long id) {#getGlyphById-long-}
```
public Glyph getGlyphById(long id)
```


Returns glyph by glyph id.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| id | long | Glyph id. |

**Returns:**
[Glyph](../../com.aspose.font/glyph) - Glyph.
### getGlyphById(GlyphId id) {#getGlyphById-com.aspose.font.GlyphId-}
```
public Glyph getGlyphById(GlyphId id)
```


Returns glyph by glyph id. Glyph id is a unique number for a glyph, which is font type dependent. Type1 Font glyph id can be instance of ( GlyphStringId ) class or ( GlyphUInt32Id ) class.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| id | [GlyphId](../../com.aspose.font/glyphid) |  |

**Returns:**
[Glyph](../../com.aspose.font/glyph)
### getAllGlyphIds() {#getAllGlyphIds--}
```
public GlyphId[] getAllGlyphIds()
```


Returns array of all glyph ids, available in the Font. Glyph id is a unique number for a glyph, which is font type dependent. Type1 Font glyph id can be instance of ( GlyphStringId ) class or ( GlyphUInt32Id ) class.

**Returns:**
com.aspose.font.GlyphId[]
### getGlyphIdType() {#getGlyphIdType--}
```
public GlyphIdType getGlyphIdType()
```


Glyph id type specification.

**Returns:**
[GlyphIdType](../../com.aspose.font/glyphidtype)
### getFontDefinition() {#getFontDefinition--}
```
public FontDefinition getFontDefinition()
```


Gets Font definition.

**Returns:**
[FontDefinition](../../com.aspose.font/fontdefinition) - Font definition.
### convert(FontType fontType) {#convert-com.aspose.font.FontType-}
```
public Font convert(FontType fontType)
```


Converts the Font into another format.

> ```
> Note: TTF Font type is now supported only.
> ```

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| fontType | [FontType](../../com.aspose.font/fonttype) | Font format type to convert into. |

**Returns:**
[Font](../../com.aspose.font/font) - Font converted into new format.
