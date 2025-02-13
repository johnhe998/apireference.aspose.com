---
title: TtfCMapFormat2Table
second_title: Aspose.Font for Java API Reference
description: Represents Format2 CMap subtable of the TTF Font file.
type: docs
weight: 65
url: /java/com.aspose.font/ttfcmapformat2table/
---
**Inheritance:**
java.lang.Object, [com.aspose.font.TtfCMapFormatBaseTable](../../com.aspose.font/ttfcmapformatbasetable)
```
public class TtfCMapFormat2Table extends TtfCMapFormatBaseTable
```

Represents Format2 CMap subtable of the TTF Font file.
## Methods

| Method | Description |
| --- | --- |
| [getGlyphIndex(long charCode)](#getGlyphIndex-long-) | Gets a glyph index for a given character code. |
| [getAllCodes()](#getAllCodes--) | Gets all the codes from current CMap's subtable. |
### getGlyphIndex(long charCode) {#getGlyphIndex-long-}
```
public long getGlyphIndex(long charCode)
```


Gets a glyph index for a given character code.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| charCode | long | Character code. |

**Returns:**
long - Glyph index.
### getAllCodes() {#getAllCodes--}
```
public ArrayList<Long> getAllCodes()
```


Gets all the codes from current CMap's subtable.

**Returns:**
java.util.ArrayList<java.lang.Long> - All the codes from current CMap's subtable.
