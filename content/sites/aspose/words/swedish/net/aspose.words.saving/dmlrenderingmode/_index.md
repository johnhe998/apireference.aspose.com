---
title: Enum DmlRenderingMode
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.DmlRenderingMode uppräkning. Anger hur DrawingMLformer renderas till fasta sidformat.
type: docs
weight: 4660
url: /sv/net/aspose.words.saving/dmlrenderingmode/
---
## DmlRenderingMode enumeration

Anger hur DrawingML-former renderas till fasta sidformat.

```csharp
public enum DmlRenderingMode
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Fallback | `0` | Om reservform är tillgänglig för DrawingML, återger Aspose.Words reservform istället för DrawingML. |
| DrawingML | `1` | Aspose.Words ignorerar fall-back formen av DrawingML och återger själva DrawingML. Detta är standardläget. |

### Exempel

Visar hur man renderar reservformer när man sparar till PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape fallbacks.docx");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Ställ in egenskapen "DmlRenderingMode" till "DmlRenderingMode.Fallback"
// för att ersätta DML-former med deras reservformer.
// Ställ in egenskapen "DmlRenderingMode" till "DmlRenderingMode.DrawingML"
// för att rendera själva DML-formerna.
options.DmlRenderingMode = dmlRenderingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLFallback.pdf", options);
```

Visar hur du konfigurerar renderingskvaliteten för DrawingML-effekter i ett dokument när vi sparar det till PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape effects.docx");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Ställ in egenskapen "DmlEffectsRenderingMode" till "DmlEffectsRenderingMode.None" för att ta bort alla DrawingML-effekter.
// Ställ in egenskapen "DmlEffectsRenderingMode" till "DmlEffectsRenderingMode.Simplified"
// för att rendera en förenklad version av DrawingML-effekter.
// Ställ in egenskapen "DmlEffectsRenderingMode" till "DmlEffectsRenderingMode.Fine" till
// gör DrawingML-effekter med mer precision och även med högre bearbetningskostnader.
options.DmlEffectsRenderingMode = effectsRenderingMode;

Assert.AreEqual(DmlRenderingMode.DrawingML, options.DmlRenderingMode);

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLEffects.pdf", options);
```

### Se även

* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


