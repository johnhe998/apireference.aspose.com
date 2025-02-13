---
title: RtfSaveOptions.SaveFormat
second_title: Aspose.Words per .NET API Reference
description: RtfSaveOptions proprietà. Specifica il formato in cui verrà salvato il documento se viene utilizzato questo oggetto opzioni di salvataggio. Può essereRtf .
type: docs
weight: 40
url: /it/net/aspose.words.saving/rtfsaveoptions/saveformat/
---
## RtfSaveOptions.SaveFormat property

Specifica il formato in cui verrà salvato il documento se viene utilizzato questo oggetto opzioni di salvataggio. Può essereRtf .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Esempi

Mostra come salvare un documento in .rtf con opzioni personalizzate.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Crea un oggetto "RtfSaveOptions" da passare al metodo "Salva" del documento per modificare il modo in cui lo salviamo in un RTF.
RtfSaveOptions options = new RtfSaveOptions();

Assert.AreEqual(SaveFormat.Rtf, options.SaveFormat);

// Imposta la proprietà "ExportCompactSize" su "true" su
// riduce le dimensioni del documento salvato a scapito della compatibilità del testo da destra a sinistra.
options.ExportCompactSize = true;

// Imposta la proprietà "ExportImagesFotOldReaders" su "true" per utilizzare parole chiave aggiuntive per garantire che il nostro documento sia
// compatibile con lettori Word 97 precedenti a Microsoft e WordPad.
// Imposta la proprietà "ExportImagesFotOldReaders" su "false" per ridurre le dimensioni del documento,
// ma impedisce ai vecchi lettori di leggere qualsiasi immagine non metafile o BMP che il documento potrebbe contenere.
options.ExportImagesForOldReaders = exportImagesForOldReaders;

doc.Save(ArtifactsDir + "RtfSaveOptions.ExportImages.rtf", options);
```

### Guarda anche

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [RtfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../rtfsaveoptions/)
* assemblea [Aspose.Words](../../../)


