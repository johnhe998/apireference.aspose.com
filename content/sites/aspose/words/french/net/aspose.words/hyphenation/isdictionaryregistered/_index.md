---
title: Hyphenation.IsDictionaryRegistered
second_title: Référence de l'API Aspose.Words pour .NET
description: Hyphenation méthode. Renvoie False si pour la langue spécifiée il ny a pas de dictionnaire enregistré ou si lenregistrement est un dictionnaire Null True sinon.
type: docs
weight: 30
url: /fr/net/aspose.words/hyphenation/isdictionaryregistered/
---
## Hyphenation.IsDictionaryRegistered method

Renvoie False si pour la langue spécifiée il n'y a pas de dictionnaire enregistré ou si l'enregistrement est un dictionnaire Null, True sinon.

```csharp
public static bool IsDictionaryRegistered(string language)
```

### Exemples

Montre comment enregistrer un dictionnaire de césure.

```csharp
// Un dictionnaire de césure contient une liste de chaînes qui définissent les règles de césure pour la langue du dictionnaire.
// Lorsqu'un document contient des lignes de texte dans lesquelles un mot peut être fractionné et continué sur la ligne suivante,
// la césure recherchera dans la liste des chaînes du dictionnaire les sous-chaînes de ce mot.
// Si le dictionnaire contient une sous-chaîne, la césure divisera le mot sur deux lignes
// par la sous-chaîne et ajouter un trait d'union à la première moitié.
// Enregistre un fichier de dictionnaire du système de fichiers local dans la locale "de-CH".
Hyphenation.RegisterDictionary("de-CH", MyDir + "hyph_de_CH.dic");

Assert.True(Hyphenation.IsDictionaryRegistered("de-CH"));

// Ouvre un document contenant du texte avec une locale correspondant à celle de notre dictionnaire,
// et enregistrez-le dans un format de sauvegarde à page fixe. Le texte de ce document comportera un trait d'union.
Document doc = new Document(MyDir + "German text.docx");

Assert.True(doc.FirstSection.Body.FirstParagraph.Runs.OfType<Run>().All(
    r => r.Font.LocaleId == new CultureInfo("de-CH").LCID));

doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Registered.pdf");

// Recharge le document après désenregistrement du dictionnaire,
// et enregistrez-le dans un autre PDF, qui n'aura pas de texte avec trait d'union.
Hyphenation.UnregisterDictionary("de-CH");

Assert.False(Hyphenation.IsDictionaryRegistered("de-CH"));

doc = new Document(MyDir + "German text.docx");
doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Unregistered.pdf");
```

### Voir également

* class [Hyphenation](../)
* espace de noms [Aspose.Words](../../hyphenation/)
* Assemblée [Aspose.Words](../../../)


