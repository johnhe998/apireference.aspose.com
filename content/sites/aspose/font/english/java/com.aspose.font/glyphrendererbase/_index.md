---
title: GlyphRendererBase
second_title: Aspose.Font for Java API Reference
description: Represents base class for glyph renderers.
type: docs
weight: 41
url: /java/com.aspose.font/glyphrendererbase/
---
**Inheritance:**
java.lang.Object

**All Implemented Interfaces:**
[com.aspose.font.IGlyphRenderer](../../com.aspose.font/iglyphrenderer)
```
public abstract class GlyphRendererBase implements IGlyphRenderer
```

Represents base class for glyph renderers.
## Methods

| Method | Description |
| --- | --- |
| [renderGlyph(IFont font, long glyphIndex)](#renderGlyph-com.aspose.font.IFont-long-) | Renders glyph |
| [renderGlyph(IFont font, long glyphIndex, TransformationMatrix glyphPlacementMatrix)](#renderGlyph-com.aspose.font.IFont-long-com.aspose.font.TransformationMatrix-) | Renders glyph. |
| [renderGlyph(IFont font, GlyphId glyphId)](#renderGlyph-com.aspose.font.IFont-com.aspose.font.GlyphId-) | Renders glyph. |
| [renderGlyph(IFont font, GlyphId glyphId, TransformationMatrix glyphPlacementMatrix)](#renderGlyph-com.aspose.font.IFont-com.aspose.font.GlyphId-com.aspose.font.TransformationMatrix-) | Renders glyph. |
| [renderGlyph(IFont font, GlyphId glyphId, Glyph glyph, TransformationMatrix glyphPlacementMatrix)](#renderGlyph-com.aspose.font.IFont-com.aspose.font.GlyphId-com.aspose.font.Glyph-com.aspose.font.TransformationMatrix-) | Renders glyph, an objective of this overloaded version - to be used with cache for glyphs. |
| [renderIndependentGlyphPath(IFont font, GlyphId glyphId, Glyph glyph, TransformationMatrix glyphPlacementMatrix)](#renderIndependentGlyphPath-com.aspose.font.IFont-com.aspose.font.GlyphId-com.aspose.font.Glyph-com.aspose.font.TransformationMatrix-) | Renders glyph using independent glyph path. |
### renderGlyph(IFont font, long glyphIndex) {#renderGlyph-com.aspose.font.IFont-long-}
```
public void renderGlyph(IFont font, long glyphIndex)
```


Renders glyph

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| font | [IFont](../../com.aspose.font/ifont) | The Font that contains the glyph. |
| glyphIndex | long | Physical glyph index inside Font. Note that this is not a unicode. |

### renderGlyph(IFont font, long glyphIndex, TransformationMatrix glyphPlacementMatrix) {#renderGlyph-com.aspose.font.IFont-long-com.aspose.font.TransformationMatrix-}
```
public void renderGlyph(IFont font, long glyphIndex, TransformationMatrix glyphPlacementMatrix)
```


Renders glyph.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| font | [IFont](../../com.aspose.font/ifont) | The Font that contains the glyph. |
| glyphIndex | long | Physical glyph index inside Font. Note that this is not a unicode. |
| glyphPlacementMatrix | [TransformationMatrix](../../com.aspose.font/transformationmatrix) | Matrix that is applied to glyph coordinates. |

### renderGlyph(IFont font, GlyphId glyphId) {#renderGlyph-com.aspose.font.IFont-com.aspose.font.GlyphId-}
```
public void renderGlyph(IFont font, GlyphId glyphId)
```


Renders glyph.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| font | [IFont](../../com.aspose.font/ifont) | The Font that contains the glyph. |
| glyphId | [GlyphId](../../com.aspose.font/glyphid) | Physical glyph index inside Font. Note that this is not a unicode. |

### renderGlyph(IFont font, GlyphId glyphId, TransformationMatrix glyphPlacementMatrix) {#renderGlyph-com.aspose.font.IFont-com.aspose.font.GlyphId-com.aspose.font.TransformationMatrix-}
```
public void renderGlyph(IFont font, GlyphId glyphId, TransformationMatrix glyphPlacementMatrix)
```


Renders glyph.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| font | [IFont](../../com.aspose.font/ifont) | The Font that contains the glyph. |
| glyphId | [GlyphId](../../com.aspose.font/glyphid) | Physical glyph index inside Font. Note that this is not a unicode. |
| glyphPlacementMatrix | [TransformationMatrix](../../com.aspose.font/transformationmatrix) | Matrix that is applied to glyph coordinates. |

### renderGlyph(IFont font, GlyphId glyphId, Glyph glyph, TransformationMatrix glyphPlacementMatrix) {#renderGlyph-com.aspose.font.IFont-com.aspose.font.GlyphId-com.aspose.font.Glyph-com.aspose.font.TransformationMatrix-}
```
public void renderGlyph(IFont font, GlyphId glyphId, Glyph glyph, TransformationMatrix glyphPlacementMatrix)
```


Renders glyph, an objective of this overloaded version - to be used with cache for glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| font | [IFont](../../com.aspose.font/ifont) | The Font that contains the glyph. |
| glyphId | [GlyphId](../../com.aspose.font/glyphid) | Physical glyph index inside Font. Note that this is not a unicode. |
| glyph | [Glyph](../../com.aspose.font/glyph) | Glyph to render. |
| glyphPlacementMatrix | [TransformationMatrix](../../com.aspose.font/transformationmatrix) | Matrix that is applied to glyph coordinates. |

### renderIndependentGlyphPath(IFont font, GlyphId glyphId, Glyph glyph, TransformationMatrix glyphPlacementMatrix) {#renderIndependentGlyphPath-com.aspose.font.IFont-com.aspose.font.GlyphId-com.aspose.font.Glyph-com.aspose.font.TransformationMatrix-}
```
public void renderIndependentGlyphPath(IFont font, GlyphId glyphId, Glyph glyph, TransformationMatrix glyphPlacementMatrix)
```


Renders glyph using independent glyph path. RenderGlyph() function family changes glyph path on rendering. It then leads to necessity reload this glyph again. This function uses copy of glyph path and doesn't changes original glyph path, so the same glyph could be reused multiple times. This version of function is intended for use with cache of glyphs.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| font | [IFont](../../com.aspose.font/ifont) | The Font that contains the glyph. |
| glyphId | [GlyphId](../../com.aspose.font/glyphid) | Physical glyph index inside Font. Note that this is not a unicode. |
| glyph | [Glyph](../../com.aspose.font/glyph) | Glyph to render. |
| glyphPlacementMatrix | [TransformationMatrix](../../com.aspose.font/transformationmatrix) | Matrix that is applied to glyph coordinates. |

