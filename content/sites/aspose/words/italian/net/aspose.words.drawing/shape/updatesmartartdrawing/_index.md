---
title: Shape.UpdateSmartArtDrawing
second_title: Aspose.Words per .NET API Reference
description: Shape metodo. Aggiorna il disegno prerenderizzato SmartArt utilizzando il motore di rendering a freddo SmartArt di Aspose.Words.
type: docs
weight: 250
url: /it/net/aspose.words.drawing/shape/updatesmartartdrawing/
---
## Shape.UpdateSmartArtDrawing method

Aggiorna il disegno prerenderizzato SmartArt utilizzando il motore di rendering a freddo SmartArt di Aspose.Words.

```csharp
public void UpdateSmartArtDrawing()
```

### Osservazioni

Microsoft Word genera e salva il disegno prerenderizzato insieme all'oggetto SmartArt. Tuttavia, se il documento viene salvato da altre applicazioni, il disegno SmartArt prerenderizzato potrebbe essere mancante o errato. Se il disegno prerenderizzato è disponibile, Aspose.Words lo usa per eseguire il rendering dell'oggetto SmartArt. Se il disegno prerenderizzato è disponibile manca quindi Aspose.Words utilizza il proprio motore di rendering a freddo SmartArt per eseguire il rendering dell'oggetto SmartArt . Se il disegno prerenderizzato non è corretto, è necessario chiamare questo metodo per richiamare il motore di rendering SmartArt cold .

### Guarda anche

* class [Shape](../)
* spazio dei nomi [Aspose.Words.Drawing](../../shape/)
* assemblea [Aspose.Words](../../../)


