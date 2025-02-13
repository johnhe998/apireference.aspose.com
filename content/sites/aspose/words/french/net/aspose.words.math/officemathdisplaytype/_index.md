---
title: Enum OfficeMathDisplayType
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Math.OfficeMathDisplayType énumération. Spécifie le type de format daffichage de léquation.
type: docs
weight: 3890
url: /fr/net/aspose.words.math/officemathdisplaytype/
---
## OfficeMathDisplayType enumeration

Spécifie le type de format d'affichage de l'équation.

```csharp
public enum OfficeMathDisplayType
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Display | `0` | L'Office Math est affiché sur sa propre ligne. |
| Inline | `1` | Office Math s'affiche en ligne avec le texte. |

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

* espace de noms [Aspose.Words.Math](../../aspose.words.math/)
* Assemblée [Aspose.Words](../../)


