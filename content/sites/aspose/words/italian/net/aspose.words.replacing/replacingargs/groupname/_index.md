---
title: ReplacingArgs.GroupName
second_title: Aspose.Words per .NET API Reference
description: ReplacingArgs proprietà. Identifica per nome un gruppo acquisito nel fileMatch che deve essere sostituito con ilReplacement stringa.
type: docs
weight: 20
url: /it/net/aspose.words.replacing/replacingargs/groupname/
---
## ReplacingArgs.GroupName property

Identifica, per nome, un gruppo acquisito nel file[`Match`](../match/) che deve essere sostituito con il[`Replacement`](../replacement/) stringa.

```csharp
public string GroupName { get; set; }
```

### Osservazioni

Quando il nome del gruppo è nullo,[`GroupIndex`](../groupindex/) serve per identificare il gruppo.

Il valore predefinito è nullo.

### Esempi

Mostra come applicare un carattere diverso al nuovo contenuto tramite FindReplaceOptions.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Font.Name = "Arial";
    builder.Writeln("Numbers that the find-and-replace operation will convert to hexadecimal and highlight:\n" +
                    "123, 456, 789 and 17379.");

    // Possiamo usare un oggetto "FindReplaceOptions" per modificare il processo di ricerca e sostituzione.
    FindReplaceOptions options = new FindReplaceOptions();

    // Imposta la proprietà "HighlightColor" su un colore di sfondo che vogliamo applicare al testo risultante dell'operazione.
    options.ApplyFont.HighlightColor = Color.LightGray;

    NumberHexer numberHexer = new NumberHexer();
    options.ReplacingCallback = numberHexer;

    int replacementCount = doc.Range.Replace(new Regex("[0-9]+"), "", options);

    Console.WriteLine(numberHexer.GetLog());

    Assert.AreEqual(4, replacementCount);
    Assert.AreEqual("Numbers that the find-and-replace operation will convert to hexadecimal and highlight:\r" +
                    "0x7B, 0x1C8, 0x315 and 0x43E3.", doc.GetText().Trim());
    Assert.AreEqual(4, doc.GetChildNodes(NodeType.Run, true).OfType<Run>()
            .Count(r => r.Font.HighlightColor.ToArgb() == Color.LightGray.ToArgb()));
}

/// <summary>
/// Sostituisce le corrispondenze numeriche di ricerca e sostituzione con i loro equivalenti esadecimali.
/// Mantiene un registro di ogni sostituzione.
/// </summary>
private class NumberHexer : IReplacingCallback
{
    public ReplaceAction Replacing(ReplacingArgs args)
    {
        mCurrentReplacementNumber++;

        int number = Convert.ToInt32(args.Match.Value);

        args.Replacement = $"0x{number:X}";

        mLog.AppendLine($"Match #{mCurrentReplacementNumber}");
        mLog.AppendLine($"\tOriginal value:\t{args.Match.Value}");
        mLog.AppendLine($"\tReplacement:\t{args.Replacement}");
        mLog.AppendLine($"\tOffset in parent {args.MatchNode.NodeType} node:\t{args.MatchOffset}");

        mLog.AppendLine(string.IsNullOrEmpty(args.GroupName)
            ? $"\tGroup index:\t{args.GroupIndex}"
            : $"\tGroup name:\t{args.GroupName}");

        return ReplaceAction.Replace;
    }

    public string GetLog()
    {
        return mLog.ToString();
    }

    private int mCurrentReplacementNumber;
    private readonly StringBuilder mLog = new StringBuilder();
}
```

### Guarda anche

* class [ReplacingArgs](../)
* spazio dei nomi [Aspose.Words.Replacing](../../replacingargs/)
* assemblea [Aspose.Words](../../../)


