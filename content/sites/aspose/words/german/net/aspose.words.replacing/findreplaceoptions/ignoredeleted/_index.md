---
title: FindReplaceOptions.IgnoreDeleted
second_title: Aspose.Words für .NET-API-Referenz
description: FindReplaceOptions eigendom. Ruft einen booleschen Wert ab oder legt ihn fest der angibt ob Text innerhalb von Löschrevisionen ignoriert werden soll. Der Standardwert istFALSCH .
type: docs
weight: 60
url: /de/net/aspose.words.replacing/findreplaceoptions/ignoredeleted/
---
## FindReplaceOptions.IgnoreDeleted property

Ruft einen booleschen Wert ab oder legt ihn fest, der angibt, ob Text innerhalb von Löschrevisionen ignoriert werden soll. Der Standardwert ist`FALSCH` .

```csharp
public bool IgnoreDeleted { get; set; }
```

### Beispiele

Zeigt, wie Text während eines Suchen-und-Ersetzen-Vorgangs in Löschrevisionen eingeschlossen oder ignoriert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

// Starten Sie die Revisionsverfolgung und entfernen Sie den zweiten Absatz, wodurch eine gelöschte Revision erstellt wird.
// Dieser Absatz bleibt im Dokument bestehen, bis wir die Löschrevision akzeptieren.
doc.StartTrackRevisions("John Doe", DateTime.Now);
doc.FirstSection.Body.Paragraphs[1].Remove();
doc.StopTrackRevisions();

Assert.True(doc.FirstSection.Body.Paragraphs[1].IsDeleteRevision);

// Wir können ein "FindReplaceOptions"-Objekt verwenden, um den Suchen- und Ersetzen-Prozess zu ändern.
FindReplaceOptions options = new FindReplaceOptions();

// Setzen Sie das "IgnoreDeleted"-Flag auf "true", um das Suchen-und-Ersetzen zu erhalten
// Operation zum Ignorieren von Absätzen, die Revisionen löschen.
// Setzen Sie das "IgnoreDeleted"-Flag auf "false", um das Suchen und Ersetzen zu erhalten
// Operation, um auch innerhalb von Löschrevisionen nach Text zu suchen.
options.IgnoreDeleted = ignoreTextInsideDeleteRevisions;

doc.Range.Replace("Hello", "Greetings", options);

Assert.AreEqual(
    ignoreTextInsideDeleteRevisions
        ? "Greetings world!\rHello again!"
        : "Greetings world!\rGreetings again!", doc.GetText().Trim());
```

### Siehe auch

* class [FindReplaceOptions](../)
* namensraum [Aspose.Words.Replacing](../../findreplaceoptions/)
* Montage [Aspose.Words](../../../)


