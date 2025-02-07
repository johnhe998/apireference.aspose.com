---
title: Enum HeaderFooterType
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.HeaderFooterType opsomming. Identifiziert den Kopf oder Fußzeilentyp in einer WordDatei.
type: docs
weight: 2940
url: /de/net/aspose.words/headerfootertype/
---
## HeaderFooterType enumeration

Identifiziert den Kopf- oder Fußzeilentyp in einer Word-Datei.

```csharp
public enum HeaderFooterType
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| HeaderEven | `0` | Kopfzeile für gerade Seiten. |
| HeaderPrimary | `1` | Primäre Kopfzeile, wird auch für ungerade Seitenzahlen verwendet. |
| FooterEven | `2` | Fußzeile für gerade Seitenzahlen. |
| FooterPrimary | `3` | Primäre Fußzeile, wird auch für ungerade Seitenzahlen verwendet. |
| HeaderFirst | `4` | Kopfzeile für die erste Seite des Abschnitts. |
| FooterFirst | `5` | Fußzeile für die erste Seite des Abschnitts. |

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

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


