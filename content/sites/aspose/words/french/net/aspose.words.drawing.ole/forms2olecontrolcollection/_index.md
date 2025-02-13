---
title: Class Forms2OleControlCollection
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Drawing.Ole.Forms2OleControlCollection classe. Représente une collection deForms2OleControl objets.
type: docs
weight: 990
url: /fr/net/aspose.words.drawing.ole/forms2olecontrolcollection/
---
## Forms2OleControlCollection class

Représente une collection de[`Forms2OleControl`](../forms2olecontrol/) objets.

```csharp
public class Forms2OleControlCollection
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [Forms2OleControlCollection](forms2olecontrolcollection/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [Count](../../aspose.words.drawing.ole/forms2olecontrolcollection/count/) { get; } | Obtient le nombre d'objets dans la collection. |
| [Item](../../aspose.words.drawing.ole/forms2olecontrolcollection/item/) { get; } | Obtient[`Forms2OleControl`](../forms2olecontrol/)objet à l'index spécifié. |

### Exemples

Montre comment accéder à un contrôle OLE incorporé dans un document et ses contrôles enfants.

```csharp
Document doc = new Document(MyDir + "OLE ActiveX controls.docm");

// Les formes stockent et affichent les objets OLE dans le corps du document.
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

Assert.AreEqual("6e182020-f460-11ce-9bcd-00aa00608e01", shape.OleFormat.Clsid.ToString());

Forms2OleControl oleControl = (Forms2OleControl)shape.OleFormat.OleControl;

// Certains contrôles OLE peuvent contenir des contrôles enfants, comme celui de ce document avec trois boutons d'options.
Forms2OleControlCollection oleControlCollection = oleControl.ChildNodes;

Assert.AreEqual(3, oleControlCollection.Count);

Assert.AreEqual("C#", oleControlCollection[0].Caption);
Assert.AreEqual("1", oleControlCollection[0].Value);

Assert.AreEqual("Visual Basic", oleControlCollection[1].Caption);
Assert.AreEqual("0", oleControlCollection[1].Value);

Assert.AreEqual("Delphi", oleControlCollection[2].Caption);
Assert.AreEqual("0", oleControlCollection[2].Value);
```

### Voir également

* espace de noms [Aspose.Words.Drawing.Ole](../../aspose.words.drawing.ole/)
* Assemblée [Aspose.Words](../../)


