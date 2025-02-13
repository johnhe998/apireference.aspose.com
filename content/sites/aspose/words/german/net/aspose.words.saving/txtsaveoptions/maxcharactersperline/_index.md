---
title: TxtSaveOptions.MaxCharactersPerLine
second_title: Aspose.Words für .NET-API-Referenz
description: TxtSaveOptions eigendom. Ruft einen ganzzahligen Wert ab oder legt ihn fest der die maximale Anzahl von Zeichen pro Zeile angibt. Der Standardwert ist 0 d. h. keine Begrenzung.
type: docs
weight: 40
url: /de/net/aspose.words.saving/txtsaveoptions/maxcharactersperline/
---
## TxtSaveOptions.MaxCharactersPerLine property

Ruft einen ganzzahligen Wert ab oder legt ihn fest, der die maximale Anzahl von Zeichen pro Zeile angibt. Der Standardwert ist 0, d. h. keine Begrenzung.

```csharp
public int MaxCharactersPerLine { get; set; }
```

### Beispiele

Zeigt, wie die maximale Anzahl von Zeichen pro Zeile eingestellt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
              "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

// Legen Sie 30 Zeichen als maximal zulässig pro Zeile fest.
TxtSaveOptions saveOptions = new TxtSaveOptions { MaxCharactersPerLine = 30 };

doc.Save(ArtifactsDir + "TxtSaveOptions.MaxCharactersPerLine.txt", saveOptions);
```

### Siehe auch

* class [TxtSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../txtsaveoptions/)
* Montage [Aspose.Words](../../../)


