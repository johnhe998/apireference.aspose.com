---
title: Class PdfDigitalSignatureTimestampSettings
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.PdfDigitalSignatureTimestampSettings classe. Contiene le impostazioni del timestamp della firma digitale.
type: docs
weight: 5170
url: /it/net/aspose.words.saving/pdfdigitalsignaturetimestampsettings/
---
## PdfDigitalSignatureTimestampSettings class

Contiene le impostazioni del timestamp della firma digitale.

```csharp
public class PdfDigitalSignatureTimestampSettings
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [PdfDigitalSignatureTimestampSettings](pdfdigitalsignaturetimestampsettings/#constructor)() | Inizializza un'istanza di questa classe. |
| [PdfDigitalSignatureTimestampSettings](pdfdigitalsignaturetimestampsettings/#constructor_1)(string, string, string) | Inizializza un'istanza di questa classe. |
| [PdfDigitalSignatureTimestampSettings](pdfdigitalsignaturetimestampsettings/#constructor_2)(string, string, string, TimeSpan) | Inizializza un'istanza di questa classe. |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Password](../../aspose.words.saving/pdfdigitalsignaturetimestampsettings/password/) { get; set; } | Password del server timestamp. |
| [ServerUrl](../../aspose.words.saving/pdfdigitalsignaturetimestampsettings/serverurl/) { get; set; } | URL server timestamp. |
| [Timeout](../../aspose.words.saving/pdfdigitalsignaturetimestampsettings/timeout/) { get; set; } | Valore di timeout per l'accesso al server timestamp. |
| [UserName](../../aspose.words.saving/pdfdigitalsignaturetimestampsettings/username/) { get; set; } | Nome utente del server timestamp. |

### Esempi

Mostra come firmare digitalmente un documento PDF salvato e contrassegnarlo con un timestamp.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Signed PDF contents.");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

 // Crea una firma digitale e assegnala al nostro oggetto SaveOptions per firmare il documento quando lo salviamo in PDF.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
options.DigitalSignatureDetails = new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "Aspose Office", DateTime.Now);

// Crea un timestamp con autorizzazione verificata.
options.DigitalSignatureDetails.TimestampSettings =
    new PdfDigitalSignatureTimestampSettings("https://freetsa.org/tsr", "JohnDoe", "MyPassword");

// La durata predefinita del timestamp è 100 secondi.
Assert.AreEqual(100.0d, options.DigitalSignatureDetails.TimestampSettings.Timeout.TotalSeconds);

// Possiamo impostare il nostro periodo di timeout tramite il costruttore.
options.DigitalSignatureDetails.TimestampSettings =
    new PdfDigitalSignatureTimestampSettings("https://freetsa.org/tsr", "JohnDoe", "MyPassword", TimeSpan.FromMinutes(30));

Assert.AreEqual(1800.0d, options.DigitalSignatureDetails.TimestampSettings.Timeout.TotalSeconds);
Assert.AreEqual("https://freetsa.org/tsr", options.DigitalSignatureDetails.TimestampSettings.ServerUrl);
Assert.AreEqual("JohnDoe", options.DigitalSignatureDetails.TimestampSettings.UserName);
Assert.AreEqual("MyPassword", options.DigitalSignatureDetails.TimestampSettings.Password);

// Il metodo "Salva" applicherà la nostra firma al documento di output in questo momento.
doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignatureTimestamp.pdf", options);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


