---
title: Enum HorizontalAlignment
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.HorizontalAlignment enum. Specifica lallineamento orizzontale di una forma mobile cornice di testo o tabella mobile.
type: docs
weight: 900
url: /it/net/aspose.words.drawing/horizontalalignment/
---
## HorizontalAlignment enumeration

Specifica l'allineamento orizzontale di una forma mobile, cornice di testo o tabella mobile.

```csharp
public enum HorizontalAlignment
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | L'oggetto è posizionato in modo esplicito, di solito usando il suo **Sono partiti** proprietà. |
| Default | `0` | ComeNone . |
| Left | `1` | Specifica che l'oggetto deve essere allineato a sinistra alla base di allineamento orizzontale. |
| Center | `2` | Specifica che l'oggetto deve essere centrato rispetto alla base di allineamento orizzontale. |
| Right | `3` | Specifica che l'oggetto deve essere allineato a destra rispetto alla base di allineamento orizzontale. |
| Inside | `4` | Specifica che l'oggetto deve trovarsi all'interno della base di allineamento orizzontale. |
| Outside | `5` | Specifica che l'oggetto deve trovarsi al di fuori della base di allineamento orizzontale. |

### Esempi

Mostra come inserire un'immagine mobile al centro di una pagina.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci un'immagine mobile che apparirà dietro il testo sovrapposto e allineala al centro della pagina.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### Guarda anche

* property [HorizontalAlignment](../shapebase/horizontalalignment/)
* spazio dei nomi [Aspose.Words.Drawing](../../aspose.words.drawing/)
* assemblea [Aspose.Words](../../)


