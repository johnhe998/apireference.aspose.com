---
title: OoxmlSaveOptions.KeepLegacyControlChars
second_title: Aspose.Words per .NET API Reference
description: OoxmlSaveOptions proprietà. Mantiene la rappresentazione originale dei caratteri di controllo legacy.
type: docs
weight: 40
url: /it/net/aspose.words.saving/ooxmlsaveoptions/keeplegacycontrolchars/
---
## OoxmlSaveOptions.KeepLegacyControlChars property

Mantiene la rappresentazione originale dei caratteri di controllo legacy.

```csharp
public bool KeepLegacyControlChars { get; set; }
```

### Esempi

Mostra come supportare i caratteri di controllo legacy durante la conversione in .docx.

```csharp
Document doc = new Document(MyDir + "Legacy control character.doc");

// Quando salviamo il documento in un formato OOXML, possiamo creare un oggetto OoxmlSaveOptions
// e quindi passalo al metodo di salvataggio del documento per modificare il modo in cui salviamo il documento.
// Imposta la proprietà "KeepLegacyControlChars" su "true" per preservare
// il carattere legacy "ShortDateTime" durante il salvataggio.
// Imposta la proprietà "KeepLegacyControlChars" su "false" per rimuoverla
// il carattere legacy "ShortDateTime" dal documento di output.
OoxmlSaveOptions so = new OoxmlSaveOptions(SaveFormat.Docx);
so.KeepLegacyControlChars = keepLegacyControlChars;

doc.Save(ArtifactsDir + "OoxmlSaveOptions.KeepLegacyControlChars.docx", so);

doc = new Document(ArtifactsDir + "OoxmlSaveOptions.KeepLegacyControlChars.docx");

Assert.AreEqual(keepLegacyControlChars ? "\u0013date \\@ \"MM/dd/yyyy\"\u0014\u0015\f" : "\u001e\f",
    doc.FirstSection.Body.GetText());
```

### Guarda anche

* class [OoxmlSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../ooxmlsaveoptions/)
* assemblea [Aspose.Words](../../../)


