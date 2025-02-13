---
title: TabStopCollection.GetPositionByIndex
second_title: Référence de l'API Aspose.Words pour .NET
description: TabStopCollection méthode. Obtient la position en points du taquet de tabulation à lindex spécifié.
type: docs
weight: 100
url: /fr/net/aspose.words/tabstopcollection/getpositionbyindex/
---
## TabStopCollection.GetPositionByIndex method

Obtient la position (en points) du taquet de tabulation à l'index spécifié.

```csharp
public double GetPositionByIndex(int index)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| index | Int32 | Un index dans la collection de taquets de tabulation. |

### Return_Value

La position du taquet de tabulation.

### Exemples

Montre comment trouver un onglet, s'arrêter à son index et vérifier sa position.

```csharp
Document doc = new Document();
TabStopCollection tabStops = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat.TabStops;

tabStops.Add(ConvertUtil.MillimeterToPoint(30), TabAlignment.Left, TabLeader.Dashes);
tabStops.Add(ConvertUtil.MillimeterToPoint(60), TabAlignment.Left, TabLeader.Dashes);

// Vérifie la position du deuxième taquet de tabulation dans la collection.
Assert.AreEqual(ConvertUtil.MillimeterToPoint(60), tabStops.GetPositionByIndex(1), 0.1d);
```

### Voir également

* class [TabStopCollection](../)
* espace de noms [Aspose.Words](../../tabstopcollection/)
* Assemblée [Aspose.Words](../../../)


