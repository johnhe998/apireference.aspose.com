---
title: DocumentVisitor.VisitEditableRangeStart
second_title: Aspose.Words för .NET API Referens
description: DocumentVisitor metod. Anropas när en början av ett redigerbart område påträffas i dokumentet.
type: docs
weight: 170
url: /sv/net/aspose.words/documentvisitor/visiteditablerangestart/
---
## DocumentVisitor.VisitEditableRangeStart method

Anropas när en början av ett redigerbart område påträffas i dokumentet.

```csharp
public virtual VisitorAction VisitEditableRangeStart(EditableRangeStart editableRangeStart)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| editableRangeStart | EditableRangeStart | Objektet som besöks. |

### Returvärde

A[`VisitorAction`](../../visitoraction/) värde som anger hur uppräkningen ska fortsätta.

### Exempel

Visar hur du skriver ut nodstrukturen för varje redigerbart område i ett dokument.

```csharp
public void EditableRangeToText()
{
    Document doc = new Document(MyDir + "DocumentVisitor-compatible features.docx");
    EditableRangeStructurePrinter visitor = new EditableRangeStructurePrinter();

    // När vi får en sammansatt nod att acceptera en dokumentbesökare, besöker besökaren den accepterande noden,
    // och sedan korsar alla nodens barn på ett djup-först sätt.
    // Besökaren kan läsa och ändra varje besökt nod.
    doc.Accept(visitor);

    Console.WriteLine(visitor.GetText());
}

/// <summary>
/// Går igenom en nods icke-binära träd av underordnade noder.
/// Skapar en karta i form av en sträng av alla påträffade EditableRange-noder och deras barn.
/// </summary>
public class EditableRangeStructurePrinter : DocumentVisitor
{
    public EditableRangeStructurePrinter()
    {
        mBuilder = new StringBuilder();
        mVisitorIsInsideEditableRange = false;
    }

    /// <summary>
    /// Hämtar vanlig text av dokumentet som samlades av besökaren.
    /// </summary>
    public string GetText()
    {
        return mBuilder.ToString();
    }

    /// <summary>
    /// Anropas när en körnod påträffas i dokumentet.
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        // Vi vill skriva ut innehållet i körningar, men bara om de är inuti former, som de skulle vara i fallet med textrutor
        if (mVisitorIsInsideEditableRange) IndentAndAppendLine("[Run] \"" + run.GetText() + "\"");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Anropas när en EditableRange-nod påträffas i dokumentet.
    /// </summary>
    public override VisitorAction VisitEditableRangeStart(EditableRangeStart editableRangeStart)
    {
        IndentAndAppendLine("[EditableRange start] ID: " + editableRangeStart.Id + " Owner: " +
                            editableRangeStart.EditableRange.SingleUser);
        mDocTraversalDepth++;
        mVisitorIsInsideEditableRange = true;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Anropas när besöket av en EditableRange-nod avslutas.
    /// </summary>
    public override VisitorAction VisitEditableRangeEnd(EditableRangeEnd editableRangeEnd)
    {
        mDocTraversalDepth--;
        IndentAndAppendLine("[EditableRange end]");
        mVisitorIsInsideEditableRange = false;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Lägg till en rad i StringBuilder och dra in den beroende på hur djupt besökaren befinner sig i dokumentträdet.
    /// </summary>
    /// <param name="text"></param>
    private void IndentAndAppendLine(string text)
    {
        for (int i = 0; i < mDocTraversalDepth; i++) mBuilder.Append("|  ");

        mBuilder.AppendLine(text);
    }

    private bool mVisitorIsInsideEditableRange;
    private int mDocTraversalDepth;
    private readonly StringBuilder mBuilder;
}
```

### Se även

* enum [VisitorAction](../../visitoraction/)
* class [EditableRangeStart](../../editablerangestart/)
* class [DocumentVisitor](../)
* namnutrymme [Aspose.Words](../../documentvisitor/)
* hopsättning [Aspose.Words](../../../)


