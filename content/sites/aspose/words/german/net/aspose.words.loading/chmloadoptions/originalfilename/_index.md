---
title: ChmLoadOptions.OriginalFileName
second_title: Aspose.Words für .NET-API-Referenz
description: ChmLoadOptions eigendom. Der Name der CHMDatei. Der Standardwert istNull .
type: docs
weight: 20
url: /de/net/aspose.words.loading/chmloadoptions/originalfilename/
---
## ChmLoadOptions.OriginalFileName property

Der Name der CHM-Datei. Der Standardwert ist`Null` .

```csharp
public string OriginalFileName { get; set; }
```

### Bemerkungen

CHM-Dokumente können Links enthalten, die nach Dateinamen auf dasselbe Dokument verweisen. Aspose.Words unterstützt solche Links und verwendet normalerweise[`OriginalFileName`](../../../aspose.words/document/originalfilename/) um zu überprüfen, ob die Datei, auf die durch einen Link verwiesen wird, die Datei ist, die gerade geladen wird. Wird ein Dokument aus einem Stream geladen, sollte sein ursprünglicher Dateiname explizit über diese Eigenschaft angegeben werden, da er nicht automatisch ermittelt werden kann.

Wenn ein CHM-Dokument aus einer Datei geladen wird und ein Wert ungleich Null für diese Eigenschaft angegeben ist, hat der Wert Vorrang vor dem tatsächlichen Namen der darin gespeicherten Datei[`OriginalFileName`](../../../aspose.words/document/originalfilename/) .

### Beispiele

Zeigt, wie URLs wie „ms-its:myfile.chm::/index.htm“ aufgelöst werden.

```csharp
// Unser Dokument enthält URLs wie "ms-its:amhelp.chm::....htm", hat aber einen anderen Namen,
// Dateiverknüpfungen funktionieren also nicht, nachdem sie in HTML gespeichert wurden.
// Wir müssen den ursprünglichen Dateinamen in 'ChmLoadOptions' definieren, um dieses Verhalten zu vermeiden.
ChmLoadOptions loadOptions = new ChmLoadOptions { OriginalFileName = "amhelp.chm" };

Document doc = new Document(new MemoryStream(File.ReadAllBytes(MyDir + "Document with ms-its links.chm")),
    loadOptions);

doc.Save(ArtifactsDir + "ExChmLoadOptions.OriginalFileName.html");
```

### Siehe auch

* class [ChmLoadOptions](../)
* namensraum [Aspose.Words.Loading](../../chmloadoptions/)
* Montage [Aspose.Words](../../../)


