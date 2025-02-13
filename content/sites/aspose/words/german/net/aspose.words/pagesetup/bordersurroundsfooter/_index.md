---
title: PageSetup.BorderSurroundsFooter
second_title: Aspose.Words für .NET-API-Referenz
description: PageSetup eigendom. Gibt an ob der Seitenrand die Fußzeile einschließt oder ausschließt.
type: docs
weight: 60
url: /de/net/aspose.words/pagesetup/bordersurroundsfooter/
---
## PageSetup.BorderSurroundsFooter property

Gibt an, ob der Seitenrand die Fußzeile einschließt oder ausschließt.

```csharp
public bool BorderSurroundsFooter { get; set; }
```

### Bemerkungen

Beachten Sie, dass sich das Ändern dieser Eigenschaft auf alle Abschnitte im Dokument auswirkt.

### Beispiele

Zeigt, wie Sie einen Rahmen auf die Seite und die Kopf-/Fußzeile anwenden.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! This is the main body text.");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("This is the header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("This is the footer.");
builder.MoveToDocumentEnd();

// Einen blauen Doppellinienrand einfügen.
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.Borders.LineStyle = LineStyle.Double;
pageSetup.Borders.Color = Color.Blue;

// Das PageSetup-Objekt eines Abschnitts hat "BorderSurroundsHeader"- und "BorderSurroundsFooter"-Flags, die bestimmen
// Ob ein Seitenrand den Haupttext umgibt, schließt auch die Kopf- bzw. Fußzeile ein.
// Setzen Sie das Flag "BorderSurroundsHeader" auf "true", um den Header mit unserem Rahmen zu umgeben,
// und dann das Flag "BorderSurroundsFooter" setzen, um die Fußzeile außerhalb des Rahmens zu lassen.
pageSetup.BorderSurroundsHeader = true;
pageSetup.BorderSurroundsFooter = false;

doc.Save(ArtifactsDir + "PageSetup.PageBorder.docx");
```

### Siehe auch

* class [PageSetup](../)
* namensraum [Aspose.Words](../../pagesetup/)
* Montage [Aspose.Words](../../../)


