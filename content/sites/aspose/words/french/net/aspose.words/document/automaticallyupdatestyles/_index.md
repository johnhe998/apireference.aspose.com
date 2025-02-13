---
title: Document.AutomaticallyUpdateStyles
second_title: Référence de l'API Aspose.Words pour .NET
description: Document propriété. Obtient ou définit un indicateur indiquant si les styles du document sont mis à jour pour correspondre aux styles du modèle joint chaque fois que le document est ouvert dans MS Word.
type: docs
weight: 30
url: /fr/net/aspose.words/document/automaticallyupdatestyles/
---
## Document.AutomaticallyUpdateStyles property

Obtient ou définit un indicateur indiquant si les styles du document sont mis à jour pour correspondre aux styles du modèle joint chaque fois que le document est ouvert dans MS Word.

```csharp
public bool AutomaticallyUpdateStyles { get; set; }
```

### Exemples

Montre comment joindre un modèle à un document.

```csharp
Document doc = new Document();

// Les documents Microsoft Word sont livrés par défaut avec un modèle joint appelé "Normal.dotm".
// Il n'y a pas de modèle par défaut pour les documents Aspose.Words vierges.
Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Attachez un modèle, puis définissez le drapeau pour appliquer les changements de style
// dans le modèle aux styles dans notre document.
doc.AttachedTemplate = MyDir + "Business brochure.dotx";
doc.AutomaticallyUpdateStyles = true;

doc.Save(ArtifactsDir + "Document.AutomaticallyUpdateStyles.docx");
```

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


