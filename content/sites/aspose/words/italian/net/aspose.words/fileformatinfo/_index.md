---
title: Class FileFormatInfo
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.FileFormatInfo classe. Contiene i dati restituiti daFileFormatUtil metodi di rilevamento del formato del documento.
type: docs
weight: 2630
url: /it/net/aspose.words/fileformatinfo/
---
## FileFormatInfo class

Contiene i dati restituiti da[`FileFormatUtil`](../fileformatutil/) metodi di rilevamento del formato del documento.

```csharp
public class FileFormatInfo
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Encoding](../../aspose.words/fileformatinfo/encoding/) { get; } | Ottiene la codifica rilevata se applicabile al formato del documento corrente. Al momento rileva la codifica solo per i documenti HTML. |
| [HasDigitalSignature](../../aspose.words/fileformatinfo/hasdigitalsignature/) { get; } | Restituisce true se questo documento contiene una firma digitale. Questa proprietà informa semplicemente che una firma digitale è presente su un documento, ma non specifica se la firma è valida o meno. |
| [IsEncrypted](../../aspose.words/fileformatinfo/isencrypted/) { get; } | Restituisce true se il documento è crittografato e richiede una password per l'apertura. |
| [LoadFormat](../../aspose.words/fileformatinfo/loadformat/) { get; } | Ottiene il formato del documento rilevato. |

### Osservazioni

Non crei direttamente istanze di questa classe. Gli oggetti di questa classe vengono restituiti da [`DetectFileFormat`](../fileformatutil/detectfileformat/)metodi.

### Esempi

Mostra come utilizzare la classe FileFormatUtil per rilevare il formato e la crittografia del documento.

```csharp
Document doc = new Document();

// Configura un oggetto SaveOptions per crittografare il documento
// con una password quando la salviamo, quindi salviamo il documento.
OdtSaveOptions saveOptions = new OdtSaveOptions(SaveFormat.Odt);
saveOptions.Password = "MyPassword";

doc.Save(ArtifactsDir + "File.DetectDocumentEncryption.odt", saveOptions);

// Verifica il tipo di file del nostro documento e il suo stato di crittografia.
FileFormatInfo info = FileFormatUtil.DetectFileFormat(ArtifactsDir + "File.DetectDocumentEncryption.odt");

Assert.AreEqual(".odt", FileFormatUtil.LoadFormatToExtension(info.LoadFormat));
Assert.True(info.IsEncrypted);
```

Mostra come utilizzare la classe FileFormatUtil per rilevare il formato del documento e la presenza di firme digitali.

```csharp
// Utilizza un'istanza FileFormatInfo per verificare che un documento non sia firmato digitalmente.
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.docx");

Assert.AreEqual(".docx", FileFormatUtil.LoadFormatToExtension(info.LoadFormat));
Assert.False(info.HasDigitalSignature);

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw", null);
DigitalSignatureUtil.Sign(MyDir + "Document.docx", ArtifactsDir + "File.DetectDigitalSignatures.docx",
    certificateHolder, new SignOptions() { SignTime = DateTime.Now });

// Usa una nuova FileFormatInstance per confermare che sia firmata.
info = FileFormatUtil.DetectFileFormat(ArtifactsDir + "File.DetectDigitalSignatures.docx");

Assert.True(info.HasDigitalSignature);

// Possiamo caricare e accedere alle firme di un documento firmato in una raccolta come questa.
Assert.AreEqual(1, DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "File.DetectDigitalSignatures.docx").Count);
```

### Guarda anche

* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


