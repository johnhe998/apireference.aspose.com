---
title: Document.AttachedTemplate
second_title: Référence de l'API Aspose.Words pour .NET
description: Document propriété. Obtient ou définit le chemin complet du modèle attaché au document.
type: docs
weight: 20
url: /fr/net/aspose.words/document/attachedtemplate/
---
## Document.AttachedTemplate property

Obtient ou définit le chemin complet du modèle attaché au document.

```csharp
public string AttachedTemplate { get; set; }
```

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Lève si vous essayez de définir une valeur nulle. |

### Remarques

Une chaîne vide signifie que le document est joint au modèle Normal.

### Exemples

Montre comment définir un modèle par défaut pour les documents qui n'ont pas de modèles joints.

```csharp
Document doc = new Document();

// Activer la mise à jour automatique du style, mais ne pas joindre de modèle de document.
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Puisqu'il n'y a pas de modèle de document, le document n'avait nulle part où suivre les changements de style.
// Utiliser un objet SaveOptions pour définir automatiquement un modèle
// si un document que nous enregistrons n'en a pas.
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### Voir également

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


