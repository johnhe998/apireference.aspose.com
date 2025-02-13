---
title: Font.SmallCaps
second_title: Référence de l'API Aspose.Words pour .NET
description: Font propriété. Vrai si la police est formatée en petites majuscules.
type: docs
weight: 360
url: /fr/net/aspose.words/font/smallcaps/
---
## Font.SmallCaps property

Vrai si la police est formatée en petites majuscules.

```csharp
public bool SmallCaps { get; set; }
```

### Exemples

Montre comment formater une exécution pour afficher son contenu en majuscules.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// Il y a deux manières d'obtenir une exécution pour afficher son texte en minuscules en majuscules sans changer le contenu.
// 1 - Définissez le drapeau AllCaps pour afficher tous les caractères en majuscules :
Run run = new Run(doc, "all capitals");
run.Font.AllCaps = true;
para.AppendChild(run);

para = (Paragraph)para.ParentNode.AppendChild(new Paragraph(doc));

// 2 - Définissez le drapeau SmallCaps pour afficher tous les caractères en petites majuscules :
// Si un caractère est en minuscule, il apparaîtra en majuscule
// mais aura la même hauteur que les minuscules (la hauteur x de la police).
// Les caractères qui étaient en majuscules à l'origine auront le même aspect.
run = new Run(doc, "Small Capitals");
run.Font.SmallCaps = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.Caps.docx");
```

### Voir également

* class [Font](../)
* espace de noms [Aspose.Words](../../font/)
* Assemblée [Aspose.Words](../../../)


