---
title: DocumentVisitor.VisitAbsolutePositionTab
second_title: Référence de l'API Aspose.Words pour .NET
description: DocumentVisitor méthode. Appelé lorsquunAbsolutePositionTab nœud est rencontré dans le document.
type: docs
weight: 10
url: /fr/net/aspose.words/documentvisitor/visitabsolutepositiontab/
---
## DocumentVisitor.VisitAbsolutePositionTab method

Appelé lorsqu'un[`AbsolutePositionTab`](../../absolutepositiontab/) nœud est rencontré dans le document.

```csharp
public virtual VisitorAction VisitAbsolutePositionTab(AbsolutePositionTab tab)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| tab | AbsolutePositionTab | L'objet visité. |

### Return_Value

UN[`VisitorAction`](../../visitoraction/) valeur qui spécifie comment poursuivre l'énumération.

### Exemples

Montre comment traiter les caractères de tabulation de position absolue avec un visiteur de document.

```csharp
public void DocumentToTxt()
{
    Document doc = new Document(MyDir + "Absolute position tab.docx");

    // Extraire le contenu textuel de notre document en acceptant ce visiteur de document personnalisé.
    DocTextExtractor myDocTextExtractor = new DocTextExtractor();
    doc.FirstSection.Body.Accept(myDocTextExtractor);

    // La tabulation de position absolue, qui n'a pas d'équivalent sous forme de chaîne, a été explicitement convertie en un caractère de tabulation.
    Assert.AreEqual("Before AbsolutePositionTab\tAfter AbsolutePositionTab", myDocTextExtractor.GetText());

    // Un AbsolutePositionTab peut également accepter un DocumentVisitor par lui-même.
    AbsolutePositionTab absPositionTab = (AbsolutePositionTab)doc.FirstSection.Body.FirstParagraph.GetChild(NodeType.SpecialChar, 0, true);

    myDocTextExtractor = new DocTextExtractor();
    absPositionTab.Accept(myDocTextExtractor);

    Assert.AreEqual("\t", myDocTextExtractor.GetText());
}

/// <summary>
/// Collecte le contenu textuel de toutes les exécutions dans le document visité. Remplace tous les caractères de tabulation absolus par des tabulations ordinaires.
/// </summary>
public class DocTextExtractor : DocumentVisitor
{
    public DocTextExtractor()
    {
        mBuilder = new StringBuilder();
    }

    /// <summary>
    /// Appelé lorsqu'un noeud Run est rencontré dans le document.
    /// </summary>
    public override VisitorAction VisitRun(Run run)
    {
        AppendText(run.Text);
        return VisitorAction.Continue;
    }

    /// <summary>
    /// Appelé lorsqu'un nœud AbsolutePositionTab est rencontré dans le document.
    /// </summary>
    public override VisitorAction VisitAbsolutePositionTab(AbsolutePositionTab tab)
    {
        mBuilder.Append("\t");
        return VisitorAction.Continue;
    }

    /// <summary>
    /// Ajoute du texte à la sortie actuelle. Honore le drapeau de sortie activé/désactivé.
    /// </summary>
    private void AppendText(string text)
    {
        mBuilder.Append(text);
    }

    /// <summary>
    /// Texte brut du document accumulé par le visiteur.
    /// </summary>
    public string GetText()
    {
        return mBuilder.ToString();
    }

    private readonly StringBuilder mBuilder;
}
```

### Voir également

* enum [VisitorAction](../../visitoraction/)
* class [AbsolutePositionTab](../../absolutepositiontab/)
* class [DocumentVisitor](../)
* espace de noms [Aspose.Words](../../documentvisitor/)
* Assemblée [Aspose.Words](../../../)


