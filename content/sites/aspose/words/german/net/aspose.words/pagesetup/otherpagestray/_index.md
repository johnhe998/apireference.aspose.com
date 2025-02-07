---
title: PageSetup.OtherPagesTray
second_title: Aspose.Words für .NET-API-Referenz
description: PageSetup eigendom. Ruft das Papierfach Fach ab oder legt es fest das für alle außer der ersten Seite eines Abschnitts verwendet werden soll. Der Wert ist implementierungs druckerspezifisch.
type: docs
weight: 290
url: /de/net/aspose.words/pagesetup/otherpagestray/
---
## PageSetup.OtherPagesTray property

Ruft das Papierfach (Fach) ab oder legt es fest, das für alle außer der ersten Seite eines Abschnitts verwendet werden soll. Der Wert ist implementierungs- (drucker-)spezifisch.

```csharp
public int OtherPagesTray { get; set; }
```

### Beispiele

Zeigt, wie Sie alle Abschnitte in einem Dokument erhalten, um das Standardpapierfach des ausgewählten Druckers zu verwenden.

```csharp
Document doc = new Document();

// Suchen Sie den Standarddrucker, den wir zum Drucken dieses Dokuments verwenden werden.
// Über die Eigenschaft "PrinterName" des PrinterSettings-Objekts können Sie einen bestimmten Drucker definieren.
PrinterSettings settings = new PrinterSettings();

// Der in Dokumenten gespeicherte Wert für das Papierfach ist druckerspezifisch.
// Dies bedeutet, dass der folgende Code alle Seitenfachwerte zurücksetzt, um das Standardfach des aktuellen Druckers zu verwenden.
// Sie können PrinterSettings.PaperSources aufzählen, um die anderen gültigen Papierfachwerte des ausgewählten Druckers zu finden.
foreach (Section section in doc.Sections.OfType<Section>())
{
    section.PageSetup.FirstPageTray = settings.DefaultPageSettings.PaperSource.RawKind;
    section.PageSetup.OtherPagesTray = settings.DefaultPageSettings.PaperSource.RawKind;
}
```

Zeigt, wie das Drucken mit unterschiedlichen Druckerfächern für unterschiedliche Papierformate eingerichtet wird.

```csharp
Document doc = new Document();

// Suchen Sie den Standarddrucker, den wir zum Drucken dieses Dokuments verwenden werden.
// Über die Eigenschaft "PrinterName" des PrinterSettings-Objekts können Sie einen bestimmten Drucker definieren.
PrinterSettings settings = new PrinterSettings();

// Dies ist das Fach, das wir für Seiten im Papierformat "A4" verwenden werden.
int printerTrayForA4 = settings.PaperSources[0].RawKind;

// Dies ist das Fach, das wir für Seiten im Papierformat "Letter" verwenden werden.
int printerTrayForLetter = settings.PaperSources[1].RawKind;

// Ändern Sie das PageSettings-Objekt dieses Abschnitts, damit Microsoft Word den Drucker anweist
// Um eines der oben identifizierten Fächer zu verwenden, abhängig von der Papiergröße dieses Abschnitts.
foreach (Section section in doc.Sections.OfType<Section>())
{
    if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.Letter)
    {
        section.PageSetup.FirstPageTray = printerTrayForLetter;
        section.PageSetup.OtherPagesTray = printerTrayForLetter;
    }
    else if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.A4)
    {
        section.PageSetup.FirstPageTray = printerTrayForA4;
        section.PageSetup.OtherPagesTray = printerTrayForA4;
    }
}
```

### Siehe auch

* class [PageSetup](../)
* namensraum [Aspose.Words](../../pagesetup/)
* Montage [Aspose.Words](../../../)


