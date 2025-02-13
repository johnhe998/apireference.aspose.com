---
title: PclSaveOptions.FallbackFontName
second_title: Aspose.Words per .NET API Reference
description: PclSaveOptions proprietà. Nome del font che verrà utilizzato se non viene trovato alcun font previsto nella stampante e nelle raccolte di font integrate.
type: docs
weight: 20
url: /it/net/aspose.words.saving/pclsaveoptions/fallbackfontname/
---
## PclSaveOptions.FallbackFontName property

Nome del font che verrà utilizzato se non viene trovato alcun font previsto nella stampante e nelle raccolte di font integrate.

```csharp
public string FallbackFontName { get; set; }
```

### Osservazioni

Se non viene trovato alcun fallback, viene generato un avviso e viene utilizzato il carattere "Arial".

### Esempi

Mostra come dichiarare un font che una stampante applicherà al testo stampato come sostituto nel caso in cui il font originale non fosse disponibile.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Non-existent font";
builder.Write("Hello world!");

PclSaveOptions saveOptions = new PclSaveOptions();
saveOptions.FallbackFontName = "Times New Roman";

// Questo documento indicherà alla stampante di applicare "Times New Roman" al testo con il carattere mancante.
// Se anche "Times New Roman" non è disponibile, la stampante utilizzerà per impostazione predefinita il carattere "Arial".
doc.Save(ArtifactsDir + "PclSaveOptions.SetPrinterFont.pcl", saveOptions);
```

### Guarda anche

* class [PclSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pclsaveoptions/)
* assemblea [Aspose.Words](../../../)


