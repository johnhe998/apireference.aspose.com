---
title: FindReplaceOptions.FindWholeWordsOnly
second_title: Aspose.Words für .NET-API-Referenz
description: FindReplaceOptions eigendom. True zeigt an dass oldValue ein eigenständiges Wort sein muss.
type: docs
weight: 50
url: /de/net/aspose.words.replacing/findreplaceoptions/findwholewordsonly/
---
## FindReplaceOptions.FindWholeWordsOnly property

True zeigt an, dass oldValue ein eigenständiges Wort sein muss.

```csharp
public bool FindWholeWordsOnly { get; set; }
```

### Beispiele

Zeigt, wie Sie eigenständige Suchen-und-Ersetzen-Operationen nur für Wörter umschalten können.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jackson will meet you in Jacksonville.");

// Wir können ein "FindReplaceOptions"-Objekt verwenden, um den Suchen-und-Ersetzen-Prozess zu ändern.
FindReplaceOptions options = new FindReplaceOptions();

// Setzen Sie das Flag "FindWholeWordsOnly" auf "true", um den gefundenen Text zu ersetzen, wenn er nicht Teil eines anderen Worts ist.
// Setzen Sie das Flag "FindWholeWordsOnly" auf "false", um den gesamten Text unabhängig von seiner Umgebung zu ersetzen.
options.FindWholeWordsOnly = findWholeWordsOnly;

doc.Range.Replace("Jackson", "Louis", options);

Assert.AreEqual(
    findWholeWordsOnly ? "Louis will meet you in Jacksonville." : "Louis will meet you in Louisville.",
    doc.GetText().Trim());
```

### Siehe auch

* class [FindReplaceOptions](../)
* namensraum [Aspose.Words.Replacing](../../findreplaceoptions/)
* Montage [Aspose.Words](../../../)


