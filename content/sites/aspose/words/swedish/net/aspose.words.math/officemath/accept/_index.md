---
title: OfficeMath.Accept
second_title: Aspose.Words för .NET API Referens
description: OfficeMath metod. Accepterar en besökare.
type: docs
weight: 70
url: /sv/net/aspose.words.math/officemath/accept/
---
## OfficeMath.Accept method

Accepterar en besökare.

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| visitor | DocumentVisitor | Besökaren som kommer att besöka noderna. |

### Returvärde

Sant om alla noder besöktes; false om DocumentVisitor stoppade operationen innan alla noder besöktes.

### Anmärkningar

Räknar upp denna nod och alla dess barn. Varje nod anropar en motsvarande metod på DocumentVisitor.

För mer information se Visitor design mönster.

Samtal[`VisitOfficeMathStart`](../../../aspose.words/documentvisitor/visitofficemathstart/) , sedan ringer[`Accept`](../../../aspose.words/node/accept/) för all underordnade noder i Office Math och samtal[`VisitOfficeMathEnd`](../../../aspose.words/documentvisitor/visitofficemathend/) i slutet.

### Exempel

Visar hur man skriver ut nodstrukturen för varje kontors matematisk nod i ett dokument.

```csharp
public void OfficeMathToText()
{
    Document doc = new Document(MyDir + "DocumentVisitor-compatible features.docx");
    OfficeMathStructurePrinter visitor = new OfficeMathStructurePrinter();

    // När vi får en sammansatt nod att acceptera en dokumentbesökare, besöker besökaren den accepterande noden,
    // och sedan korsar alla nodens barn på ett djup-först sätt.
    // Besökaren kan läsa och ändra varje besökt nod.
    doc.Accept(visitor);

    Console.WriteLine(visitor.GetText());
}

/// <summary>
/// Går igenom en nods icke-binära träd av underordnade noder.
/// Skapar en karta i form av en sträng av alla påträffade OfficeMath-noder och deras barn.
/// </summary>
public class OfficeMathStructurePrinter : DocumentVisitor
{
    public OfficeMathStructurePrinter()
    {
        mBuilder = new StringBuilder();
        mVisitorIsInsideOfficeMath = false;
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
        if (mVisitorIsInsideOfficeMath) IndentAndAppendLine("[Run] \"" + run.GetText() + "\"");

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Anropas när en OfficeMath-nod påträffas i dokumentet.
    /// </summary>
    public override VisitorAction VisitOfficeMathStart(OfficeMath officeMath)
    {
        IndentAndAppendLine("[OfficeMath start] Math object type: " + officeMath.MathObjectType);
        mDocTraversalDepth++;
        mVisitorIsInsideOfficeMath = true;

        return VisitorAction.Continue;
    }

    /// <summary>
    /// Anropas efter att alla undernoder i en OfficeMath-nod har besökts.
    /// </summary>
    public override VisitorAction VisitOfficeMathEnd(OfficeMath officeMath)
    {
        mDocTraversalDepth--;
        IndentAndAppendLine("[OfficeMath end]");
        mVisitorIsInsideOfficeMath = false;

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

    private bool mVisitorIsInsideOfficeMath;
    private int mDocTraversalDepth;
    private readonly StringBuilder mBuilder;
}
```

### Se även

* class [DocumentVisitor](../../../aspose.words/documentvisitor/)
* class [OfficeMath](../)
* namnutrymme [Aspose.Words.Math](../../officemath/)
* hopsättning [Aspose.Words](../../../)


