---
title: ViewOptions.DoNotDisplayPageBoundaries
second_title: Aspose.Words für .NET-API-Referenz
description: ViewOptions eigendom. Deaktiviert die Anzeige des Abstands zwischen dem oberen Rand des Textes und dem oberen Rand der Seite.
type: docs
weight: 20
url: /de/net/aspose.words.settings/viewoptions/donotdisplaypageboundaries/
---
## ViewOptions.DoNotDisplayPageBoundaries property

Deaktiviert die Anzeige des Abstands zwischen dem oberen Rand des Textes und dem oberen Rand der Seite.

```csharp
public bool DoNotDisplayPageBoundaries { get; set; }
```

### Beispiele

Zeigt, wie vertikale Leerzeichen und Kopf-/Fußzeilen in Ansichtsoptionen ausgeblendet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inhalt einfügen, der sich über 3 Seiten erstreckt.
builder.Writeln("Paragraph 1, Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Paragraph 2, Page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Paragraph 3, Page 3.");

// Kopf- und Fußzeile einfügen.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("This is the header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("This is the footer.");

// Dieses Dokument enthält eine kleine Menge an Inhalten, die einige ganze Seiten Platz einnehmen.
// Setzen Sie das "DoNotDisplayPageBoundaries"-Flag auf "true", damit ältere Versionen von Microsoft Word Kopfzeilen auslassen,
// Fußzeilen und ein Großteil der vertikalen Leerzeichen bei der Anzeige unseres Dokuments.
// Setzen Sie das Flag "DoNotDisplayPageBoundaries" auf "false", um ältere Versionen von Microsoft Word zu erhalten
// um unser Dokument normal anzuzeigen.
doc.ViewOptions.DoNotDisplayPageBoundaries = doNotDisplayPageBoundaries;

doc.Save(ArtifactsDir + "ViewOptions.DisplayPageBoundaries.doc");
```

### Siehe auch

* class [ViewOptions](../)
* namensraum [Aspose.Words.Settings](../../viewoptions/)
* Montage [Aspose.Words](../../../)


