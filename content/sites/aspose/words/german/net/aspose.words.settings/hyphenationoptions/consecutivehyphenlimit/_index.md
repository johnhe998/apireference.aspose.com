---
title: HyphenationOptions.ConsecutiveHyphenLimit
second_title: Aspose.Words für .NET-API-Referenz
description: HyphenationOptions eigendom. Ermittelt oder setzt die maximale Anzahl aufeinanderfolgender Zeilen die mit Bindestrichen enden können. Der Standardwert für diese Eigenschaft ist 0.
type: docs
weight: 30
url: /de/net/aspose.words.settings/hyphenationoptions/consecutivehyphenlimit/
---
## HyphenationOptions.ConsecutiveHyphenLimit property

Ermittelt oder setzt die maximale Anzahl aufeinanderfolgender Zeilen, die mit Bindestrichen enden können. Der Standardwert für diese Eigenschaft ist 0.

```csharp
public int ConsecutiveHyphenLimit { get; set; }
```

### Bemerkungen

Wenn der Wert dieser Eigenschaft auf 0 gesetzt ist, können beliebig viele aufeinanderfolgende Zeilen mit Bindestrichen enden.

Beim Speichern in festen Seitenformaten, zB PDF, hat die Eigenschaft keine Auswirkung.

### Beispiele

Zeigt, wie die automatische Silbentrennung konfiguriert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 24;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.HyphenationOptions.AutoHyphenation = true;
doc.HyphenationOptions.ConsecutiveHyphenLimit = 2;
doc.HyphenationOptions.HyphenationZone = 720;
doc.HyphenationOptions.HyphenateCaps = true;

doc.Save(ArtifactsDir + "Document.HyphenationOptions.docx");
```

### Siehe auch

* class [HyphenationOptions](../)
* namensraum [Aspose.Words.Settings](../../hyphenationoptions/)
* Montage [Aspose.Words](../../../)


