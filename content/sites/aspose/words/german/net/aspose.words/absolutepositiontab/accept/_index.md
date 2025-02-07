---
title: AbsolutePositionTab.Accept
second_title: Aspose.Words für .NET-API-Referenz
description: AbsolutePositionTab methode. Akzeptiert einen Besucher.
type: docs
weight: 10
url: /de/net/aspose.words/absolutepositiontab/accept/
---
## AbsolutePositionTab.Accept method

Akzeptiert einen Besucher.

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| visitor | DocumentVisitor | Der Besucher, der den Knoten besucht. |

### Rückgabewert

False, wenn der Besucher angefordert hat, dass die Enumeration beendet wird.

### Bemerkungen

Ruft DocumentVisitor.VisitAbsolutePositionTab auf.

Weitere Informationen finden Sie im Besucher-Entwurfsmuster.

### Beispiele

Zeigt, wie Tabulatorzeichen mit absoluter Position mit einem Dokumentbesucher verarbeitet werden.

```csharp
public void DocumentToTxt()
{
    Document doc = new Document(MyDir + "Absolute position tab.docx");

    // Extrahieren Sie den Textinhalt unseres Dokuments, indem Sie diesen benutzerdefinierten Dokumentbesucher akzeptieren.
    DocTextExtractor myDocTextExtractor = new DocTextExtractor();
    doc.FirstSection.Body.Accept(myDocTextExtractor);

    // Die absolute Position tab, die kein Äquivalent in Zeichenfolgenform hat, wurde explizit in ein Tabulatorzeichen umgewandelt.
    Assert.AreEqual("Before AbsolutePositionTab\tAfter AbsolutePositionTab", myDocTextExtractor.GetText());

    // Ein AbsolutePositionTab kann auch selbst einen DocumentVisitor akzeptieren.
    AbsolutePositionTab absPositionTab = (AbsolutePositionTab)doc.FirstSection.Body.FirstParagraph.GetChild(NodeType.SpecialChar, 0, true);

    myDocTextExtractor = new DocTextExtractor();
    absPositionTab.Accept(myDocTextExtractor);

    Assert.AreEqual("\t", myDocTextExtractor.GetText());
}

/// <summary>
/// Sammelt den Textinhalt aller Läufe im besuchten Dokument. Ersetzt alle absoluten Tabulatorzeichen durch gewöhnliche Tabulatoren.
/// </summary>
public class DocTextExtractor : DocumentVisitor
{
    public DocTextExtractor()
    {
        mBuilder = new StringBuilder();
    }

    /// <summary>
    /// Wird aufgerufen, wenn im Dokument ein Run-Knoten gefunden wird.
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        AppendText(run.Text);
        return VisitorAction.Continue;
    }

    /// <summary>
    /// Wird aufgerufen, wenn im Dokument ein AbsolutePositionTab-Knoten gefunden wird.
    /// </summary>
    public override VisitorAction VisitAbsolutePositionTab(AbsolutePositionTab tab)
    {
        mBuilder.Append("\t");
        return VisitorAction.Continue;
    }

    /// <summary>
    /// Fügt Text zur aktuellen Ausgabe hinzu. Berücksichtigt das aktivierte/deaktivierte Ausgangsflag.
    /// </summary>
    private void AppendText(string text)
    {
        mBuilder.Append(text);
    }

    /// <summary>
    /// Klartext des Dokuments, das vom Besucher gesammelt wurde.
    /// </summary>
    public string GetText()
    {
        return mBuilder.ToString();
    }

    private readonly StringBuilder mBuilder;
}
```

### Siehe auch

* class [DocumentVisitor](../../documentvisitor/)
* class [AbsolutePositionTab](../)
* namensraum [Aspose.Words](../../absolutepositiontab/)
* Montage [Aspose.Words](../../../)


