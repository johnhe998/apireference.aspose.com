---
title: NodeList.Count
second_title: Référence de l'API Aspose.Words pour .NET
description: NodeList propriété. Obtient le nombre de nœuds dans la liste.
type: docs
weight: 10
url: /fr/net/aspose.words/nodelist/count/
---
## NodeList.Count property

Obtient le nombre de nœuds dans la liste.

```csharp
public int Count { get; }
```

### Exemples

Montre comment utiliser XPaths pour naviguer dans une NodeList.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérer des nœuds avec un DocumentBuilder.
builder.Writeln("Hello world!");

builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndTable();

#if NET48 || JAVA
builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
#elif NET5_0_OR_GREATER || __MOBILE__
using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
    builder.InsertImage(image);
#endif

// Notre document contient trois nœuds Run.
NodeList nodeList = doc.SelectNodes("//Courir");

Assert.AreEqual(3, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Hello world!"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// Utilisez une double barre oblique pour sélectionner tous les nœuds d'exécution
// qui sont des descendants indirects d'un nœud Table, qui seraient les exécutions à l'intérieur des deux cellules que nous avons insérées.
nodeList = doc.SelectNodes("//Table//Courir");

Assert.AreEqual(2, nodeList.Count);
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 1"));
Assert.True(nodeList.Any(n => n.GetText().Trim() == "Cell 2"));

// Les barres obliques simples spécifient les relations descendantes directes,
// que nous avons sauté lorsque nous avons utilisé des doubles barres obliques.
Assert.AreEqual(doc.SelectNodes(" //Table//Exécuter"),
    doc.SelectNodes("//Table/Ligne/Cellule/Paragraphe/Exécuter") );

// Accéder à la forme qui contient l'image que nous avons insérée.
nodeList = doc.SelectNodes("//Forme");

Assert.AreEqual(1, nodeList.Count);

Shape shape = (Shape)nodeList[0];
Assert.True(shape.HasImage);
```

### Voir également

* class [NodeList](../)
* espace de noms [Aspose.Words](../../nodelist/)
* Assemblée [Aspose.Words](../../../)


