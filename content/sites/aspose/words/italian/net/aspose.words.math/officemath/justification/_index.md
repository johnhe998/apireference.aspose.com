---
title: OfficeMath.Justification
second_title: Aspose.Words per .NET API Reference
description: OfficeMath proprietà. Ottiene/imposta la giustificazione di Office Math.
type: docs
weight: 30
url: /it/net/aspose.words.math/officemath/justification/
---
## OfficeMath.Justification property

Ottiene/imposta la giustificazione di Office Math.

```csharp
public OfficeMathJustification Justification { get; set; }
```

### Osservazioni

La giustificazione non può essere impostata su Office Math con il tipo di formato di visualizzazioneInline.

Non è possibile impostare la giustificazione in linea su Office Math con il tipo di formato di visualizzazioneDisplay.

Corrispondente[`DisplayType`](../displaytype/) deve essere impostato prima di impostare la giustificazione di Office Math.

### Esempi

Mostra come impostare la formattazione della visualizzazione matematica dell'ufficio.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath) doc.GetChild(NodeType.OfficeMath, 0, true);

// I nodi OfficeMath che sono figli di altri nodi OfficeMath sono sempre inline.
// Il nodo con cui stiamo lavorando è il nodo base per cambiarne la posizione e il tipo di visualizzazione.
Assert.AreEqual(MathObjectType.OMathPara, officeMath.MathObjectType);
Assert.AreEqual(NodeType.OfficeMath, officeMath.NodeType);
Assert.AreEqual(officeMath.ParentNode, officeMath.ParentParagraph);

// I formati OOXML e WML utilizzano la proprietà "EquationXmlEncoding".
Assert.IsNull(officeMath.EquationXmlEncoding);

// Modifica la posizione e il tipo di visualizzazione del nodo OfficeMath.
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

doc.Save(ArtifactsDir + "Shape.OfficeMath.docx");
```

### Guarda anche

* enum [OfficeMathJustification](../../officemathjustification/)
* class [OfficeMath](../)
* spazio dei nomi [Aspose.Words.Math](../../officemath/)
* assemblea [Aspose.Words](../../../)


