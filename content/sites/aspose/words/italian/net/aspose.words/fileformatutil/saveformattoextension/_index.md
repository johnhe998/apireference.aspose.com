---
title: FileFormatUtil.SaveFormatToExtension
second_title: Aspose.Words per .NET API Reference
description: FileFormatUtil metodo. Converte un valore enumerato del formato di salvataggio in unestensione di file. Lestensione restituita è una stringa minuscola con un punto iniziale.
type: docs
weight: 80
url: /it/net/aspose.words/fileformatutil/saveformattoextension/
---
## FileFormatUtil.SaveFormatToExtension method

Converte un valore enumerato del formato di salvataggio in un'estensione di file. L'estensione restituita è una stringa minuscola con un punto iniziale.

```csharp
public static string SaveFormatToExtension(SaveFormat saveFormat)
```

### Eccezioni

| eccezione | condizione |
| --- | --- |
| ArgumentException | Lancia quando non può convertire. |

### Osservazioni

IlWordML il valore viene convertito in ".wml".

IlFlatOpc il valore viene convertito in ".fopc".

### Esempi

Mostra come utilizzare i metodi FileFormatUtil per rilevare il formato di un documento.

```csharp
// Carica un documento da un file a cui manca un'estensione, quindi rileva il formato del file.
using (FileStream docStream = File.OpenRead(MyDir + "Word document with missing file extension"))
{
    FileFormatInfo info = FileFormatUtil.DetectFileFormat(docStream);
    LoadFormat loadFormat = info.LoadFormat;

    Assert.AreEqual(LoadFormat.Doc, loadFormat);

    // Di seguito sono riportati due metodi per convertire un LoadFormat nel corrispondente SaveFormat.
    // 1 - Ottieni la stringa di estensione del file per LoadFormat, quindi ottieni il corrispondente SaveFormat da quella stringa:
    string fileExtension = FileFormatUtil.LoadFormatToExtension(loadFormat);
    SaveFormat saveFormat = FileFormatUtil.ExtensionToSaveFormat(fileExtension);

    // 2 - Converti LoadFormat direttamente nel suo SaveFormat:
    saveFormat = FileFormatUtil.LoadFormatToSaveFormat(loadFormat);

    // Carica un documento dallo stream, quindi salvalo con l'estensione file rilevata automaticamente.
    Document doc = new Document(docStream);

    Assert.AreEqual(".doc", FileFormatUtil.SaveFormatToExtension(saveFormat));

    doc.Save(ArtifactsDir + "File.SaveToDetectedFileFormat" + FileFormatUtil.SaveFormatToExtension(saveFormat));
}
```

### Guarda anche

* enum [SaveFormat](../../saveformat/)
* class [FileFormatUtil](../)
* spazio dei nomi [Aspose.Words](../../fileformatutil/)
* assemblea [Aspose.Words](../../../)


