---
title: StyleCollection.AddCopy
second_title: Référence de l'API Aspose.Words pour .NET
description: StyleCollection méthode. Copie un style dans cette collection.
type: docs
weight: 70
url: /fr/net/aspose.words/stylecollection/addcopy/
---
## StyleCollection.AddCopy method

Copie un style dans cette collection.

```csharp
public Style AddCopy(Style style)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| style | Style | Style à copier. |

### Return_Value

Style copié prêt à l'emploi.

### Remarques

Le style à copier peut appartenir au même document ainsi qu'à un document différent.

Le style lié est copié.

Cette méthode ne copie pas les styles de base.

Si la collection contient déjà un style avec le même nom, alors le nouveau nom est généré automatiquement en ajoutant le suffixe "_number" à partir de 0, par exemple "Normal_0", "Heading 1_1" etc. Use[`Name`](../../style/name/) setter pour changer le nom du style importé.

### Exemples

Montre comment importer un style d'un document dans un autre document.

```csharp
Document srcDoc = new Document();

// Crée un style personnalisé pour le document source.
Style srcStyle = srcDoc.Styles.Add(StyleType.Paragraph, "MyStyle");
srcStyle.Font.Color = Color.Red;

// Importe le style personnalisé du document source dans le document de destination.
Document dstDoc = new Document();
Style newStyle = dstDoc.Styles.AddCopy(srcStyle);

// Le style importé a une apparence identique à son style source.
Assert.AreEqual("MyStyle", newStyle.Name);
Assert.AreEqual(Color.Red.ToArgb(), newStyle.Font.Color.ToArgb());
```

Montre comment cloner le style d'un document.

```csharp
Document doc = new Document();

// La méthode AddCopy crée une copie du style spécifié et
// génère automatiquement un nouveau nom pour le style, tel que "Titre 1_0".
Style newStyle = doc.Styles.AddCopy(doc.Styles["Heading 1"]);

// Utilisez la propriété "Name" du style pour changer le nom d'identification du style.
newStyle.Name = "My Heading 1";

// Notre document a maintenant deux styles identiques avec des noms différents.
// La modification des paramètres de l'un des styles n'affecte pas l'autre.
newStyle.Font.Color = Color.Red;

Assert.AreEqual("My Heading 1", newStyle.Name);
Assert.AreEqual("Heading 1", doc.Styles["Heading 1"].Name);

Assert.AreEqual(doc.Styles["Heading 1"].Type, newStyle.Type);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Name, newStyle.Font.Name);
Assert.AreEqual(doc.Styles["Heading 1"].Font.Size, newStyle.Font.Size);
Assert.AreNotEqual(doc.Styles["Heading 1"].Font.Color, newStyle.Font.Color);
```

### Voir également

* class [Style](../../style/)
* class [StyleCollection](../)
* espace de noms [Aspose.Words](../../stylecollection/)
* Assemblée [Aspose.Words](../../../)


