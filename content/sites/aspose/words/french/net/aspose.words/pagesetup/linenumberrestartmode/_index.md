---
title: PageSetup.LineNumberRestartMode
second_title: Référence de l'API Aspose.Words pour .NET
description: PageSetup propriété. Obtient ou définit la manière dont la numérotation des lignes sexécute cestàdire si elle recommence au début dune nouvelle page ou section ou sexécute en continu.
type: docs
weight: 230
url: /fr/net/aspose.words/pagesetup/linenumberrestartmode/
---
## PageSetup.LineNumberRestartMode property

Obtient ou définit la manière dont la numérotation des lignes s'exécute, c'est-à-dire si elle recommence au début d'une nouvelle page ou section ou s'exécute en continu.

```csharp
public LineNumberRestartMode LineNumberRestartMode { get; set; }
```

### Exemples

Montre comment activer la numérotation des lignes pour une section.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Nous pouvons utiliser l'objet PageSetup de la section pour afficher les nombres à gauche des lignes de texte de la section.
// C'est le même comportement qu'un objet List,
// mais il couvre toute la section et ne modifie en rien le texte.
// Notre section va recommencer la numérotation à chaque nouvelle page à partir de 1 et afficher le numéro,
// si c'est un multiple de 3, à 50pt à gauche de la ligne.
PageSetup pageSetup = builder.PageSetup;
pageSetup.LineStartingNumber = 1;
pageSetup.LineNumberCountBy = 3;
pageSetup.LineNumberRestartMode = LineNumberRestartMode.RestartPage;
pageSetup.LineNumberDistanceFromText = 50.0d;

for (int i = 1; i <= 25; i++)
    builder.Writeln($"Line {i}.");

// Le compteur de lignes ignorera tout paragraphe avec le drapeau "SuppressLineNumbers" défini sur "true".
// Ce paragraphe est sur la 15ème ligne, qui est un multiple de 3, et afficherait donc normalement un numéro de ligne.
// Le compteur de lignes de la section ignorera également cette ligne, traitera la ligne suivante comme la 15e,
// et continuer le décompte à partir de ce point.
doc.FirstSection.Body.Paragraphs[14].ParagraphFormat.SuppressLineNumbers = true;

doc.Save(ArtifactsDir + "PageSetup.LineNumbers.docx");
```

### Voir également

* enum [LineNumberRestartMode](../../linenumberrestartmode/)
* class [PageSetup](../)
* espace de noms [Aspose.Words](../../pagesetup/)
* Assemblée [Aspose.Words](../../../)


