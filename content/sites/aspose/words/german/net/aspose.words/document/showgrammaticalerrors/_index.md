---
title: Document.ShowGrammaticalErrors
second_title: Aspose.Words für .NET-API-Referenz
description: Document eigendom. Gibt an ob Grammatikfehler in diesem Dokument angezeigt werden sollen.
type: docs
weight: 370
url: /de/net/aspose.words/document/showgrammaticalerrors/
---
## Document.ShowGrammaticalErrors property

Gibt an, ob Grammatikfehler in diesem Dokument angezeigt werden sollen.

```csharp
public bool ShowGrammaticalErrors { get; set; }
```

### Beispiele

Zeigt, wie Fehler im Dokument angezeigt/ausgeblendet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie zwei Sätze mit Fehlern ein, die aufgegriffen würden
// durch die Rechtschreib- und Grammatikprüfung in Microsoft Word.
builder.Writeln("There is a speling error in this sentence.");
builder.Writeln("Their is a grammatical error in this sentence.");

// Wenn diese Optionen aktiviert sind, werden Rechtschreibfehler unterstrichen
// im Ausgabedokument durch eine gezackte rote Linie und eine doppelte blaue Linie hebt Grammatikfehler hervor.
doc.ShowGrammaticalErrors = showErrors;
doc.ShowSpellingErrors = showErrors;

doc.Save(ArtifactsDir + "Document.SpellingAndGrammarErrors.docx");
```

### Siehe auch

* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


