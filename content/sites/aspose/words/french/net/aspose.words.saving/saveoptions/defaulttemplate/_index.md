---
title: SaveOptions.DefaultTemplate
second_title: Référence de l'API Aspose.Words pour .NET
description: SaveOptions propriété. Obtient ou définit le chemin daccès au modèle par défaut y compris le nom de fichier. La valeur par défaut de cette propriété est chaîne vide Empty .
type: docs
weight: 40
url: /fr/net/aspose.words.saving/saveoptions/defaulttemplate/
---
## SaveOptions.DefaultTemplate property

Obtient ou définit le chemin d'accès au modèle par défaut (y compris le nom de fichier). La valeur par défaut de cette propriété est **chaîne vide** (Empty ).

```csharp
public string DefaultTemplate { get; set; }
```

### Remarques

S'il est spécifié, ce chemin est utilisé pour charger le modèle lorsque[`AutomaticallyUpdateStyles`](../../../aspose.words/document/automaticallyupdatestyles/) est vrai, mais[`AttachedTemplate`](../../../aspose.words/document/attachedtemplate/) est vide.

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

* class [SaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../saveoptions/)
* Assemblée [Aspose.Words](../../../)


