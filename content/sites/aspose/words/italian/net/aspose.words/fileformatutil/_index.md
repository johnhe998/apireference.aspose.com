---
title: Class FileFormatUtil
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.FileFormatUtil classe. Fornisce metodi di utilità per lavorare con i formati di file come il rilevamento del formato di file o la conversione di estensioni di file in/da enumerazioni di formati di file.
type: docs
weight: 2640
url: /it/net/aspose.words/fileformatutil/
---
## FileFormatUtil class

Fornisce metodi di utilità per lavorare con i formati di file, come il rilevamento del formato di file o la conversione di estensioni di file in/da enumerazioni di formati di file.

```csharp
public static class FileFormatUtil
```

## Metodi

| Nome | Descrizione |
| --- | --- |
| static [ContentTypeToLoadFormat](../../aspose.words/fileformatutil/contenttypetoloadformat/)(string) | Converte il tipo di contenuto IANA in un valore enumerato del formato di caricamento. |
| static [ContentTypeToSaveFormat](../../aspose.words/fileformatutil/contenttypetosaveformat/)(string) | Converte il tipo di contenuto IANA in un formato di salvataggio enumerato valore. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat)(Stream) | Rileva e restituisce le informazioni su un formato di un documento archiviato in uno stream. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat_1)(string) | Rileva e restituisce le informazioni su un formato di un documento archiviato in un file su disco. |
| static [ExtensionToSaveFormat](../../aspose.words/fileformatutil/extensiontosaveformat/)(string) | Converte un'estensione del nome file in a[`SaveFormat`](../saveformat/) valore. |
| static [ImageTypeToExtension](../../aspose.words/fileformatutil/imagetypetoextension/)(ImageType) | Converte un valore enumerato del tipo di immagine Aspose.Words in un'estensione di file. L'estensione restituita è una stringa minuscola con un punto iniziale. |
| static [LoadFormatToExtension](../../aspose.words/fileformatutil/loadformattoextension/)(LoadFormat) | Converte un valore enumerato del formato di caricamento in un'estensione di file. L'estensione restituita è una stringa minuscola con un punto iniziale. |
| static [LoadFormatToSaveFormat](../../aspose.words/fileformatutil/loadformattosaveformat/)(LoadFormat) | Converte a[`LoadFormat`](../loadformat/) valore ad a[`SaveFormat`](../saveformat/) valore se possibile. |
| static [SaveFormatToExtension](../../aspose.words/fileformatutil/saveformattoextension/)(SaveFormat) | Converte un valore enumerato del formato di salvataggio in un'estensione di file. L'estensione restituita è una stringa minuscola con un punto iniziale. |
| static [SaveFormatToLoadFormat](../../aspose.words/fileformatutil/saveformattoloadformat/)(SaveFormat) | Converte a[`SaveFormat`](../saveformat/) valore ad a[`LoadFormat`](../loadformat/) valore se possibile. |

### Esempi

Mostra come rilevare la codifica in un file html.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.html");

Assert.AreEqual(LoadFormat.Html, info.LoadFormat);

// La proprietà Encoding viene utilizzata solo quando creiamo un oggetto FileFormatInfo per un documento html.
Assert.AreEqual("Western European (Windows)", info.Encoding.EncodingName);
Assert.AreEqual(1252, info.Encoding.CodePage);
```

### Guarda anche

* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


