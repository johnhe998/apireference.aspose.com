---
title: Document.UpdateWordCount
second_title: Référence de l'API Aspose.Words pour .NET
description: Document méthode. Met à jour les propriétés de nombre de mots du document.
type: docs
weight: 770
url: /fr/net/aspose.words/document/updatewordcount/
---
## UpdateWordCount() {#updatewordcount}

Met à jour les propriétés de nombre de mots du document.

```csharp
public void UpdateWordCount()
```

### Remarques

**Mettre à jour le nombre de mots** recalcule et met à jour les propriétés Caractères, Mots et Paragraphes dans le[`BuiltInDocumentProperties`](../builtindocumentproperties/) collecte de la **Document**.

Notez que **Mettre à jour le nombre de mots** ne met pas à jour les propriétés du nombre de lignes et de pages. Utilisez le`UpdateWordCount` surchargez et passez la valeur True en tant que paramètre pour le faire.

Lorsque vous utilisez une version d'évaluation, le filigrane d'évaluation sera également inclus dans le nombre de mots.

### Exemples

Montre comment mettre à jour toutes les étiquettes de liste dans un document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
builder.Write("Ut enim ad minim veniam, " +
                "quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

// Aspose.Words ne suit pas les métriques de document comme celles-ci en temps réel.
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Paragraphs);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

// Pour obtenir des valeurs précises pour trois de ces propriétés, nous devrons les mettre à jour manuellement.
doc.UpdateWordCount();

Assert.AreEqual(196, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(36, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(2, doc.BuiltInDocumentProperties.Paragraphs);

// Pour le nombre de lignes, nous devrons appeler une surcharge spécifique de la méthode de mise à jour.
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

doc.UpdateWordCount(true);

Assert.AreEqual(4, doc.BuiltInDocumentProperties.Lines);
```

### Voir également

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)

---

## UpdateWordCount(bool) {#updatewordcount_1}

Met à jour les propriétés de nombre de mots du document, éventuellement mises à jour[`Lines`](../../../aspose.words.properties/builtindocumentproperties/lines/) propriété.

```csharp
public void UpdateWordCount(bool updateLinesCount)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| updateLinesCount | Boolean | Vrai si le nombre de lignes dans le document doit être calculé. |

### Remarques

Cette méthode reconstruira la mise en page du document.

### Exemples

Montre comment mettre à jour toutes les étiquettes de liste dans un document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
builder.Write("Ut enim ad minim veniam, " +
                "quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

// Aspose.Words ne suit pas les métriques de document comme celles-ci en temps réel.
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Paragraphs);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

// Pour obtenir des valeurs précises pour trois de ces propriétés, nous devrons les mettre à jour manuellement.
doc.UpdateWordCount();

Assert.AreEqual(196, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(36, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(2, doc.BuiltInDocumentProperties.Paragraphs);

// Pour le nombre de lignes, nous devrons appeler une surcharge spécifique de la méthode de mise à jour.
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

doc.UpdateWordCount(true);

Assert.AreEqual(4, doc.BuiltInDocumentProperties.Lines);
```

### Voir également

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


