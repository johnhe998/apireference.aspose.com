---
title: PageSetup.OddAndEvenPagesHeaderFooter
second_title: Aspose.Words für .NET-API-Referenz
description: PageSetup eigendom. WAHRwenn das Dokument unterschiedliche Kopf und Fußzeilen für ungerade und gerade Seiten hat.
type: docs
weight: 270
url: /de/net/aspose.words/pagesetup/oddandevenpagesheaderfooter/
---
## PageSetup.OddAndEvenPagesHeaderFooter property

**WAHR**wenn das Dokument unterschiedliche Kopf- und Fußzeilen für ungerade und gerade Seiten hat.

```csharp
public bool OddAndEvenPagesHeaderFooter { get; set; }
```

### Bemerkungen

Beachten Sie, dass sich das Ändern dieser Eigenschaft auf alle Abschnitte im Dokument auswirkt.

### Beispiele

Zeigt, wie Kopf- und Fußzeilen in einem Dokument mit DocumentBuilder erstellt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Geben Sie an, dass wir unterschiedliche Kopf- und Fußzeilen für die erste, gerade und ungerade Seite wünschen.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Kopfzeilen erstellen, dann drei Seiten zum Dokument hinzufügen, um jeden Kopfzeilentyp anzuzeigen.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page3");

doc.Save(ArtifactsDir + "DocumentBuilder.HeadersAndFooters.docx");
```

Zeigt, wie Kopf-/Fußzeilen gerader Seiten aktiviert oder deaktiviert werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Unten sind zwei Arten von Kopf-/Fußzeilen.
// 1 - Die "primäre" Kopf-/Fußzeile, die auf jeder Seite im Abschnitt erscheint.
// Wir können die primäre Kopf-/Fußzeile durch eine erste und eine gerade Seiten-Kopf-/Fußzeile überschreiben.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("Primary header.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("Primary footer.");

// 2 - Die "gerade" Kopf-/Fußzeile, die auf jeder geraden Seite dieses Abschnitts erscheint.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Writeln("Even page header.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterEven);
builder.Writeln("Even page footer.");

builder.MoveToSection(0);
builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// Jeder Abschnitt hat ein "PageSetup"-Objekt, das Eigenschaften bezüglich des Aussehens der Seite festlegt
// wie Ausrichtung, Größe und Rahmen.
// Setzen Sie die Eigenschaft "OddAndEvenPagesHeaderFooter" auf "true"
// um die Kopf-/Fußzeile der geraden Seite auf geraden Seiten anzuzeigen.
// Setzen Sie die Eigenschaft "OddAndEvenPagesHeaderFooter" auf "false"
// um die primäre Kopf-/Fußzeile auf geraden Seiten anzuzeigen.
builder.PageSetup.OddAndEvenPagesHeaderFooter = oddAndEvenPagesHeaderFooter;

doc.Save(ArtifactsDir + "PageSetup.OddAndEvenPagesHeaderFooter.docx");
```

### Siehe auch

* class [PageSetup](../)
* namensraum [Aspose.Words](../../pagesetup/)
* Montage [Aspose.Words](../../../)


