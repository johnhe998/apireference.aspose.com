---
title: Enum TextureAlignment
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.TextureAlignment enum. Specifica lallineamento per la piastrellatura del riempimento della trama.
type: docs
weight: 1220
url: /it/net/aspose.words.drawing/texturealignment/
---
## TextureAlignment enumeration

Specifica l'allineamento per la piastrellatura del riempimento della trama.

```csharp
public enum TextureAlignment
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| TopLeft | `0` | Allineamento texture in alto a sinistra. |
| Top | `1` | Allineamento texture superiore. |
| TopRight | `2` | Allineamento texture in alto a destra. |
| Left | `3` | Allineamento texture a sinistra. |
| Center | `4` | Allineamento texture al centro. |
| Right | `5` | Allineamento texture corretto. |
| BottomLeft | `6` | Allineamento texture in basso a sinistra. |
| Bottom | `7` | Allineamento della trama inferiore. |
| BottomRight | `8` | Allineamento texture in basso a destra. |
| None | `9` | Nessuno allineamento texture. |

### Esempi

Mostra come riempire e affiancare la trama all'interno della forma.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);

// Applica l'allineamento della trama al riempimento della forma.
shape.Fill.PresetTextured(PresetTexture.Canvas);
shape.Fill.TextureAlignment = TextureAlignment.TopRight;

// Usa l'opzione di conformità per definire la forma usando DML se vuoi ottenere "TextureAlignment"
// proprietà dopo il salvataggio del documento.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.TextureFill.docx", saveOptions);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Drawing](../../aspose.words.drawing/)
* assemblea [Aspose.Words](../../)


