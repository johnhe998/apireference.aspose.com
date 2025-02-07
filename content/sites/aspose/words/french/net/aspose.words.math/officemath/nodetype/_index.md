---
title: OfficeMath.NodeType
second_title: Référence de l'API Aspose.Words pour .NET
description: OfficeMath propriété. Retours NodeType.OfficeMathNodeType.OfficeMath .
type: docs
weight: 50
url: /fr/net/aspose.words.math/officemath/nodetype/
---
## OfficeMath.NodeType property

Retours **NodeType.OfficeMathNodeType.OfficeMath** .

```csharp
public override NodeType NodeType { get; }
```

### Exemples

Montre comment définir la mise en forme de l'affichage mathématique de bureau.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath) doc.GetChild(NodeType.OfficeMath, 0, true);

// Les nœuds OfficeMath qui sont des enfants d'autres nœuds OfficeMath sont toujours en ligne.
// Le nœud avec lequel nous travaillons est le nœud de base pour changer son emplacement et son type d'affichage.
Assert.AreEqual(MathObjectType.OMathPara, officeMath.MathObjectType);
Assert.AreEqual(NodeType.OfficeMath, officeMath.NodeType);
Assert.AreEqual(officeMath.ParentNode, officeMath.ParentParagraph);

// Les formats OOXML et WML utilisent la propriété "EquationXmlEncoding".
Assert.IsNull(officeMath.EquationXmlEncoding);

// Modifier l'emplacement et le type d'affichage du nœud OfficeMath.
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

doc.Save(ArtifactsDir + "Shape.OfficeMath.docx");
```

### Voir également

* enum [NodeType](../../../aspose.words/nodetype/)
* class [OfficeMath](../)
* espace de noms [Aspose.Words.Math](../../officemath/)
* Assemblée [Aspose.Words](../../../)


