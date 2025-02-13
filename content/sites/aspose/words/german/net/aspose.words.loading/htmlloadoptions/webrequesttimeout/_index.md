---
title: HtmlLoadOptions.WebRequestTimeout
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlLoadOptions eigendom. Die Anzahl der zu wartenden Millisekunden bevor die Webanforderung abläuft. Der Standardwert ist 100000 Millisekunden 100 Sekunden.
type: docs
weight: 70
url: /de/net/aspose.words.loading/htmlloadoptions/webrequesttimeout/
---
## HtmlLoadOptions.WebRequestTimeout property

Die Anzahl der zu wartenden Millisekunden, bevor die Webanforderung abläuft. Der Standardwert ist 100000 Millisekunden (100 Sekunden).

```csharp
public int WebRequestTimeout { get; set; }
```

### Bemerkungen

Die Anzahl der Millisekunden, die Aspose.Words auf eine Antwort wartet, wenn externe Ressourcen (Bilder, style Sheets) geladen werden, die in HTML- und MHTML-Dokumenten verlinkt sind.

### Beispiele

Zeigt, wie Sie ein Zeitlimit für Webanfragen festlegen, wenn Sie ein Dokument mit externen Ressourcen laden, die über URLs verknüpft sind.

```csharp
{
    // Erstellen Sie ein neues HtmlLoadOptions-Objekt und überprüfen Sie seinen Timeout-Schwellenwert für eine Webanforderung.
    HtmlLoadOptions options = new HtmlLoadOptions();

    // Beim Laden eines HTML-Dokuments mit Ressourcen, die extern durch eine Webadressen-URL verknüpft sind,
    // Aspose.Words bricht Webanfragen ab, die die Ressourcen nicht innerhalb dieses Zeitlimits in Millisekunden abrufen können.
    Assert.AreEqual(100000, options.WebRequestTimeout);

    // Setzen Sie einen WarningCallback, der alle Warnungen aufzeichnet, die während des Ladens auftreten.
    ListDocumentWarnings warningCallback = new ListDocumentWarnings();
    options.WarningCallback = warningCallback;

    // Laden Sie ein solches Dokument und überprüfen Sie, ob eine Form mit Bilddaten erstellt wurde.
    // Zum Laden dieses verlinkten Bildes ist eine Webanfrage erforderlich, die innerhalb unseres Zeitlimits abgeschlossen sein muss.
    string html = $@"
        <html>
            <img src=""{ImageUrl}"" alt=""Aspose logo"" style=""width:400px;height:400px;"">
        </html>
    ";

    // Legen Sie ein unangemessenes Timeout-Limit fest und versuchen Sie, das Dokument erneut zu laden.
    options.WebRequestTimeout = 0;
    Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), options);
    Assert.AreEqual(2, warningCallback.Warnings().Count);

    // Eine Webanforderung, die innerhalb des Zeitlimits kein Bild erhält, erzeugt dennoch ein Bild.
    // Das Bild wird jedoch das rote 'x' sein, das üblicherweise fehlende Bilder anzeigt.
    Shape imageShape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
    Assert.AreEqual(924, imageShape.ImageData.ImageBytes.Length);

    // Wir können auch einen benutzerdefinierten Rückruf konfigurieren, um alle Warnungen von Webanfragen mit Zeitüberschreitung abzufangen.
    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[0].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[0].WarningType);
    Assert.AreEqual($"Couldn't load a resource from \'{ImageUrl}\'.", warningCallback.Warnings()[0].Description);

    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[1].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[1].WarningType);
    Assert.AreEqual("Image has been replaced with a placeholder.", warningCallback.Warnings()[1].Description);

    doc.Save(ArtifactsDir + "HtmlLoadOptions.WebRequestTimeout.docx");
}

/// <summary>
/// Speichert alle Warnungen, die während eines Dokumentladevorgangs auftreten, in einer Liste.
/// </summary>
private class ListDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        mWarnings.Add(info);
    }

    public List<WarningInfo> Warnings() { 
        return mWarnings;
    }

    private readonly List<WarningInfo> mWarnings = new List<WarningInfo>();
}
```

### Siehe auch

* class [HtmlLoadOptions](../)
* namensraum [Aspose.Words.Loading](../../htmlloadoptions/)
* Montage [Aspose.Words](../../../)


