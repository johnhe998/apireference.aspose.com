---
title: INodeChangingCallback.NodeRemoving
second_title: Aspose.Words för .NET API Referens
description: INodeChangingCallback metod. Anropas precis innan en nod som tillhör detta dokument är på väg att tas bort från dokumentet.
type: docs
weight: 40
url: /sv/net/aspose.words/inodechangingcallback/noderemoving/
---
## INodeChangingCallback.NodeRemoving method

Anropas precis innan en nod som tillhör detta dokument är på väg att tas bort från dokumentet.

```csharp
public void NodeRemoving(NodeChangingArgs args)
```

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

* class [NodeChangingArgs](../../nodechangingargs/)
* interface [INodeChangingCallback](../)
* namnutrymme [Aspose.Words](../../inodechangingcallback/)
* hopsättning [Aspose.Words](../../../)


