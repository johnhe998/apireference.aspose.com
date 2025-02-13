---
title: Document.Compliance
second_title: Référence de l'API Aspose.Words pour .NET
description: Document propriété. Obtient la version de conformité OOXML déterminée à partir du contenu du document chargé. Na de sens que pour les documents OOXML.
type: docs
weight: 60
url: /fr/net/aspose.words/document/compliance/
---
## Document.Compliance property

Obtient la version de conformité OOXML déterminée à partir du contenu du document chargé. N'a de sens que pour les documents OOXML.

```csharp
public OoxmlCompliance Compliance { get; }
```

### Remarques

Si vous avez créé un nouveau document vierge ou chargé un document non OOXML renvoie leEcma376_2006 évaluer.

### Exemples

Montre comment lire la version de conformité Open Office XML d'un document chargé.

```csharp
// La version de conformité varie entre les documents créés par différentes versions de Microsoft Word.
Document doc = new Document(MyDir + "Document.doc");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Ecma376_2006);

doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Iso29500_2008_Transitional);
```

### Voir également

* enum [OoxmlCompliance](../../../aspose.words.saving/ooxmlcompliance/)
* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


