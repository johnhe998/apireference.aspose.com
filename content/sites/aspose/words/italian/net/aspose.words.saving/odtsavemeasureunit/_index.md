---
title: Enum OdtSaveMeasureUnit
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.OdtSaveMeasureUnit enum. Unità di misura specificate da applicare al contenuto del documento misurabile come forma larghezze e altro durante il salvataggio.
type: docs
weight: 5040
url: /it/net/aspose.words.saving/odtsavemeasureunit/
---
## OdtSaveMeasureUnit enumeration

Unità di misura specificate da applicare al contenuto del documento misurabile come forma, larghezze e altro durante il salvataggio.

```csharp
public enum OdtSaveMeasureUnit
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Centimeters | `0` | Specifica che il contenuto del documento viene salvato utilizzando centimetri. |
| Inches | `1` | Specifica che il contenuto del documento viene salvato utilizzando pollici. |

### Esempi

Mostra come utilizzare diverse unità di misura per definire i parametri di stile di un documento ODT salvato.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Quando esportiamo il documento in .odt, possiamo usare un oggetto OdtSaveOptions per modificare il modo in cui salviamo il documento.
// Possiamo impostare la proprietà "MeasureUnit" su "OdtSaveMeasureUnit.Centimeters"
// per definire contenuto come parametri di stile utilizzando il sistema di metriche utilizzato da Open Office. 
// Possiamo impostare la proprietà "MeasureUnit" su "OdtSaveMeasureUnit.Inches"
// per definire contenuto come parametri di stile utilizzando il sistema imperiale, utilizzato da Microsoft Word.
OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = odtSaveMeasureUnit
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


