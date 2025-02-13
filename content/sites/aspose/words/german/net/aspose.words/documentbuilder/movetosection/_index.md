---
title: DocumentBuilder.MoveToSection
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder methode. Bewegt den Cursor an den Anfang des Hauptteils in einem bestimmten Abschnitt.
type: docs
weight: 550
url: /de/net/aspose.words/documentbuilder/movetosection/
---
## DocumentBuilder.MoveToSection method

Bewegt den Cursor an den Anfang des Hauptteils in einem bestimmten Abschnitt.

```csharp
public void MoveToSection(int sectionIndex)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| sectionIndex | Int32 | Der Index des Abschnitts, zu dem verschoben werden soll. |

### Bemerkungen

Wenn sectionIndex größer oder gleich 0 ist, gibt er einen Index from am Anfang des Dokuments an, wobei 0 der erste Abschnitt ist. Wenn sectionIndex kleiner als 0, ist, wurde ein Index vom Ende des Dokuments angegeben, wobei -1 der letzte Abschnitt ist.

Der Cursor wird auf den ersten Absatz in der bewegt **Körper** des angegebenen Abschnitts.

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

* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


