---
title: RtfSaveOptions.ExportImagesForOldReaders
second_title: Aspose.Words per .NET API Reference
description: RtfSaveOptions proprietà. Specifica se le parole chiave per vecchi lettori vengono scritte o meno in RTF. Ciò può influire in modo significativo sulla dimensione del documento RTF. Il valore predefinito èVERO .
type: docs
weight: 30
url: /it/net/aspose.words.saving/rtfsaveoptions/exportimagesforoldreaders/
---
## RtfSaveOptions.ExportImagesForOldReaders property

Specifica se le parole chiave per "vecchi lettori" vengono scritte o meno in RTF. Ciò può influire in modo significativo sulla dimensione del documento RTF. Il valore predefinito è`VERO` .

```csharp
public bool ExportImagesForOldReaders { get; set; }
```

### Osservazioni

I "vecchi lettori" sono applicazioni precedenti a Microsoft Word 97 e anche WordPad. Quando questa opzione è`VERO` Aspose.Words scrive parole chiave RTF aggiuntive. Queste parole chiave consentono di visualizzare correttamente il documento quando viene aperto in un'applicazione "vecchio lettore" , ma possono aumentare notevolmente le dimensioni del documento.

Se imposti questa opzione su`falso`, in "vecchi lettori" verranno visualizzate solo le immagini nei formati WMF, EMF e BMP .

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

* class [RtfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../rtfsaveoptions/)
* assemblea [Aspose.Words](../../../)


