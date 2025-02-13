---
title: OfficeMath.Justification
second_title: Référence de l'API Aspose.Words pour .NET
description: OfficeMath propriété. Obtient/définit la justification Office Math.
type: docs
weight: 30
url: /fr/net/aspose.words.math/officemath/justification/
---
## OfficeMath.Justification property

Obtient/définit la justification Office Math.

```csharp
public OfficeMathJustification Justification { get; set; }
```

### Remarques

La justification ne peut pas être définie sur Office Math avec le type de format d'affichageInline.

La justification en ligne ne peut pas être définie sur Office Math avec le type de format d'affichageDisplay.

Correspondant[`DisplayType`](../displaytype/) doit être défini avant de définir la justification Office Math.

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

* enum [OfficeMathJustification](../../officemathjustification/)
* class [OfficeMath](../)
* espace de noms [Aspose.Words.Math](../../officemath/)
* Assemblée [Aspose.Words](../../../)


