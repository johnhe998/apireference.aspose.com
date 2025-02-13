---
title: Watermark.SetImage
second_title: Aspose.Words för .NET API Referens
description: Watermark metod. Lägger till bildvattenstämpel i dokumentet.
type: docs
weight: 30
url: /sv/net/aspose.words/watermark/setimage/
---
## SetImage(Image) {#setimage}

Lägger till bildvattenstämpel i dokumentet.

```csharp
public void SetImage(Image image)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| image | Image | Bild som visas som en vattenstämpel. |

### Undantag

| undantag | skick |
| --- | --- |
| ArgumentNullException | Kastar när bilden är null. |

### Se även

* class [Watermark](../)
* namnutrymme [Aspose.Words](../../watermark/)
* hopsättning [Aspose.Words](../../../)

---

## SetImage(Image, ImageWatermarkOptions) {#setimage_1}

Lägger till bildvattenstämpel i dokumentet.

```csharp
public void SetImage(Image image, ImageWatermarkOptions options)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| image | Image | Bild som visas som en vattenstämpel. |
| options | ImageWatermarkOptions | Definierar ytterligare alternativ för bildens vattenstämpel. |

### Undantag

| undantag | skick |
| --- | --- |
| ArgumentNullException | Kastar när bilden är null. |

### Anmärkningar

Om[`ImageWatermarkOptions`](../../imagewatermarkoptions/) är null, kommer vattenstämpeln att ställas in med standardalternativ.

### Exempel

Visar hur man skapar en vattenstämpel från en bild i det lokala filsystemet.

```csharp
Document doc = new Document();

            // Ändra bildens vattenmärkes utseende med ett ImageWatermarkOptions-objekt,
            // skicka den sedan medan du skapar en vattenstämpel från en bildfil.
            ImageWatermarkOptions imageWatermarkOptions = new ImageWatermarkOptions();
            imageWatermarkOptions.Scale = 5;
            imageWatermarkOptions.IsWashout = false;

#if NET48 || JAVA
            doc.Watermark.SetImage(Image.FromFile(ImageDir + "Logo.jpg"), imageWatermarkOptions);
#elif NET5_0_OR_GREATER || __MOBILE__
            using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
            {
                doc.Watermark.SetImage(image, imageWatermarkOptions);
            }
#endif

            doc.Save(ArtifactsDir + "Document.ImageWatermark.docx");
```

### Se även

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* namnutrymme [Aspose.Words](../../watermark/)
* hopsättning [Aspose.Words](../../../)

---

## SetImage(string, ImageWatermarkOptions) {#setimage_2}

Lägger till bildvattenstämpel i dokumentet.

```csharp
public void SetImage(string imagePath, ImageWatermarkOptions options)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| imagePath | String | Sökväg till bildfilen som visas som en vattenstämpel. |
| options | ImageWatermarkOptions | Definierar ytterligare alternativ för bildens vattenstämpel. |

### Undantag

| undantag | skick |
| --- | --- |
| ArgumentNullException | Kastar när sökvägen är null. |

### Anmärkningar

Om[`ImageWatermarkOptions`](../../imagewatermarkoptions/) är null, kommer vattenstämpeln att ställas in med standardalternativ.

### Se även

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* namnutrymme [Aspose.Words](../../watermark/)
* hopsättning [Aspose.Words](../../../)


