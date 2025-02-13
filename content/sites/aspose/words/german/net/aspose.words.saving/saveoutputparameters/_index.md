---
title: Class SaveOutputParameters
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.SaveOutputParameters klas. Dieses Objekt wird an den Aufrufer zurückgegeben nachdem ein Dokument gespeichert wurde und enthält zusätzliche Informationen die während des Speichervorgangs generiert oder berechnet wurden. Der Aufrufer kann dieses Objekt verwenden oder ignorieren.
type: docs
weight: 5310
url: /de/net/aspose.words.saving/saveoutputparameters/
---
## SaveOutputParameters class

Dieses Objekt wird an den Aufrufer zurückgegeben, nachdem ein Dokument gespeichert wurde, und enthält zusätzliche Informationen, die während des Speichervorgangs generiert oder berechnet wurden. Der Aufrufer kann dieses Objekt verwenden oder ignorieren.

```csharp
public class SaveOutputParameters
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [ContentType](../../aspose.words.saving/saveoutputparameters/contenttype/) { get; } | Gibt den Content-Type-String (Internet Media Type) zurück, der den Typ des gespeicherten Dokuments identifiziert. |

### Beispiele

Zeigt, wie auf die Ausgabeparameter des Speichervorgangs eines Dokuments zugegriffen wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Nachdem wir ein Dokument gespeichert haben, können wir auf den Internet Media Type (MIME-Typ) des neu erstellten Ausgabedokuments zugreifen.
SaveOutputParameters parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.doc");

Assert.AreEqual("application/msword", parameters.ContentType);

// Diese Eigenschaft ändert sich je nach Speicherformat.
parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.pdf");

Assert.AreEqual("application/pdf", parameters.ContentType);
```

### Siehe auch

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


