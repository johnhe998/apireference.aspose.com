---
title: Class NodeChangingArgs
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.NodeChangingArgs klass. Tillhandahåller data för metoder förINodeChangingCallback gränssnitt.
type: docs
weight: 3950
url: /sv/net/aspose.words/nodechangingargs/
---
## NodeChangingArgs class

Tillhandahåller data för metoder för[`INodeChangingCallback`](../inodechangingcallback/) gränssnitt.

```csharp
public class NodeChangingArgs
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Action](../../aspose.words/nodechangingargs/action/) { get; } | Får ett värde som indikerar vilken typ av nodändringshändelse som inträffar. |
| [NewParent](../../aspose.words/nodechangingargs/newparent/) { get; } | Hämtar nodens överordnade som kommer att ställas in efter att operationen är klar. |
| [Node](../../aspose.words/nodechangingargs/node/) { get; } | Får[`Node`](./node/) som läggs till eller tas bort. |
| [OldParent](../../aspose.words/nodechangingargs/oldparent/) { get; } | Hämtar nodens förälder innan operationen började. |

### Exempel

Visar hur du anpassar nodbyte med en återuppringning.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Ställ in noden ändra callback till anpassad implementering,
    // lägg sedan till/ta bort noder för att få den att generera en logg.
    HandleNodeChangingFontChanger callback = new HandleNodeChangingFontChanger();
    doc.NodeChangingCallback = callback;

    builder.Writeln("Hello world!");
    builder.Writeln("Hello again!");
    builder.InsertField(" HYPERLINK \"https://www.google.com/\" ");
    builder.InsertShape(ShapeType.Rectangle, 300, 300);

    doc.Range.Fields[0].Remove();

    Console.WriteLine(callback.GetLog());

/// <summary>
/// Loggar datum och tid för varje nod insättning och borttagning.
/// Ställer in ett anpassat teckensnittsnamn/storlek för textinnehållet i Run-noder.
/// </summary>
public class HandleNodeChangingFontChanger : INodeChangingCallback
{
    void INodeChangingCallback.NodeInserted(NodeChangingArgs args)
    {
        mLog.AppendLine($"\tType:\t{args.Node.NodeType}");
        mLog.AppendLine($"\tHash:\t{args.Node.GetHashCode()}");

        if (args.Node.NodeType == NodeType.Run)
        {
            Aspose.Words.Font font = ((Run) args.Node).Font;
            mLog.Append($"\tFont:\tChanged from \"{font.Name}\" {font.Size}pt");

            font.Size = 24;
            font.Name = "Arial";

            mLog.AppendLine($" to \"{font.Name}\" {font.Size}pt");
            mLog.AppendLine($"\tContents:\n\t\t\"{args.Node.GetText()}\"");
        }
    }

    void INodeChangingCallback.NodeInserting(NodeChangingArgs args)
    {
        mLog.AppendLine($"\n{DateTime.Now:dd/MM/yyyy HH:mm:ss:fff}\tNode insertion:");
    }

    void INodeChangingCallback.NodeRemoved(NodeChangingArgs args)
    {
        mLog.AppendLine($"\tType:\t{args.Node.NodeType}");
        mLog.AppendLine($"\tHash code:\t{args.Node.GetHashCode()}");
    }

    void INodeChangingCallback.NodeRemoving(NodeChangingArgs args)
    {
        mLog.AppendLine($"\n{DateTime.Now:dd/MM/yyyy HH:mm:ss:fff}\tNode removal:");
    }

    public string GetLog()
    {
        return mLog.ToString();
    }

    private readonly StringBuilder mLog = new StringBuilder();
}
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


