---
title: RecognitionSettings
second_title: Aspose.OCR for .NET API Reference
description: Initializes a new instance of the RecognitionSettingsaspose.ocr/recognitionsettings class with auto skew  true.
type: docs
weight: 10
url: /net/aspose.ocr/recognitionsettings/recognitionsettings/
---
## RecognitionSettings() {#constructor}

Initializes a new instance of the [`RecognitionSettings`](../../recognitionsettings) class with auto skew = true.

```csharp
public RecognitionSettings()
```

### See Also

* class [RecognitionSettings](../../recognitionsettings)
* namespace [Aspose.OCR](../../recognitionsettings)
* assembly [Aspose.OCR](../../../)

---

## RecognitionSettings(Language, List&lt;Rectangle&gt;, bool, float, bool, int) {#constructor_1}

Initializes a new instance of the [`RecognitionSettings`](../../recognitionsettings) class with full set of properties.

```csharp
public RecognitionSettings(Language language = Language.None, 
    List<Rectangle> recognitionAreas = null, bool autoSkew = true, float skewAngle = 0, 
    bool recognizeSingleLine = false, int threshold = 0)
```

| Parameter | Type | Description |
| --- | --- | --- |
| language | Language | Language used for OCR. |
| recognitionAreas | List`1 | Manually set areas for recognition. Null by default - means whole image is processed. |
| autoSkew | Boolean | Enable automatic image skew correction. |
| skewAngle | Single | Set angle for image rotation. |
| recognizeSingleLine | Boolean | For single-line images |
| threshold | Int32 | Custom image binarization threshold |

### See Also

* enum [Language](../../language)
* class [RecognitionSettings](../../recognitionsettings)
* namespace [Aspose.OCR](../../recognitionsettings)
* assembly [Aspose.OCR](../../../)

---

## RecognitionSettings(bool) {#constructor_2}

Initializes a new instance of the [`RecognitionSettings`](../../recognitionsettings) class with auto skew.

```csharp
public RecognitionSettings(bool autoSkew)
```

| Parameter | Type | Description |
| --- | --- | --- |
| autoSkew | Boolean | Enable automatic image skew correction. |

### See Also

* class [RecognitionSettings](../../recognitionsettings)
* namespace [Aspose.OCR](../../recognitionsettings)
* assembly [Aspose.OCR](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.OCR.dll -->
