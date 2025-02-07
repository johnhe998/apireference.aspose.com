---
title: Section.Accept
second_title: Référence de l'API Aspose.Words pour .NET
description: Section méthode. Accepte un visiteur.
type: docs
weight: 70
url: /fr/net/aspose.words/section/accept/
---
## Section.Accept method

Accepte un visiteur.

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| visitor | DocumentVisitor | Le visiteur qui visitera les nœuds. |

### Return_Value

Vrai si tous les nœuds ont été visités ; false si DocumentVisitor a arrêté l'opération avant de visiter tous les nœuds.

### Remarques

Énumère ce nœud et tous ses enfants. Chaque nœud appelle une méthode correspondante sur DocumentVisitor.

Pour plus d'informations, consultez le modèle de conception Visiteur.

Appelle DocumentVisitor.VisitSectionStart, puis appelle Accept pour tous les nœuds enfants de la section et appelle DocumentVisitor.VisitSectionEnd à la fin.

### Voir également

* class [DocumentVisitor](../../documentvisitor/)
* class [Section](../)
* espace de noms [Aspose.Words](../../section/)
* Assemblée [Aspose.Words](../../../)


