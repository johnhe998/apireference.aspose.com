---
title: LoadOptions.BaseUri
second_title: Aspose.Words für .NET-API-Referenz
description: LoadOptions eigendom. Ruft die Zeichenfolge ab oder legt sie fest die verwendet wird um im Dokument gefundene relative URIs bei Bedarf in absolute URIs aufzulösen. Kann null oder eine leere Zeichenfolge sein. Standard ist null.
type: docs
weight: 20
url: /de/net/aspose.words.loading/loadoptions/baseuri/
---
## LoadOptions.BaseUri property

Ruft die Zeichenfolge ab oder legt sie fest, die verwendet wird, um im Dokument gefundene relative URIs bei Bedarf in absolute URIs aufzulösen. Kann null oder eine leere Zeichenfolge sein. Standard ist null.

```csharp
public string BaseUri { get; set; }
```

### Bemerkungen

Diese Eigenschaft wird verwendet, um relative URIs in den folgenden Fällen in absolute aufzulösen:

1. Wenn ein HTML-Dokument aus einem Stream geladen wird und das Dokument Bilder mit relativen URIs enthält und kein Basis-URI im BASE-HTML-Element angegeben ist.
2. Beim Speichern eines Dokuments in PDF und anderen Formaten zum Abrufen von Bildern, die mit relativen URIs verknüpft sind, damit die Bilder im Ausgabedokument gespeichert werden können.

### Beispiele

Zeigt, wie ein HTML-Dokument mit Bildern aus einem Stream mit einem Basis-URI geöffnet wird.

```csharp
using (Stream stream = File.OpenRead(MyDir + "Document.html"))
{
    // Beim Laden den URI des Basisordners übergeben
    // damit alle Bilder mit relativen URIs im HTML-Dokument gefunden werden können.
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.BaseUri = ImageDir;

    Document doc = new Document(stream, loadOptions);

    // Prüfen, ob die erste Form des Dokuments ein gültiges Bild enthält.
    Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

    Assert.IsTrue(shape.IsImage);
    Assert.IsNotNull(shape.ImageData.ImageBytes);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Width), 0.01);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Height), 0.01);
}
```

### Siehe auch

* class [LoadOptions](../)
* namensraum [Aspose.Words.Loading](../../loadoptions/)
* Montage [Aspose.Words](../../../)


