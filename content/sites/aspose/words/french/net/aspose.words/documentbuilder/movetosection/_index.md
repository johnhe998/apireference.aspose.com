---
title: DocumentBuilder.MoveToSection
second_title: Référence de l'API Aspose.Words pour .NET
description: DocumentBuilder méthode. Déplace le curseur au début du corps dans une section spécifiée.
type: docs
weight: 550
url: /fr/net/aspose.words/documentbuilder/movetosection/
---
## DocumentBuilder.MoveToSection method

Déplace le curseur au début du corps dans une section spécifiée.

```csharp
public void MoveToSection(int sectionIndex)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| sectionIndex | Int32 | L'index de la section vers laquelle se déplacer. |

### Remarques

Lorsque sectionIndex est supérieur ou égal à 0, il spécifie un index depuis le début du document, 0 étant la première section. Lorsque sectionIndex est inférieur à 0, , il spécifie un index à partir de la fin du document, -1 étant la dernière section.

Le curseur est déplacé vers le premier paragraphe de la **Corps** de la section spécifiée.

### Exemples

Montre comment créer des en-têtes et des pieds de page dans un document à l'aide de DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Spécifiez que nous voulons des en-têtes et des pieds de page différents pour les premières pages, paires et impaires.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Crée les en-têtes, puis ajoute trois pages au document pour afficher chaque type d'en-tête.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page3");

doc.Save(ArtifactsDir + "DocumentBuilder.HeadersAndFooters.docx");
```

### Voir également

* class [DocumentBuilder](../)
* espace de noms [Aspose.Words](../../documentbuilder/)
* Assemblée [Aspose.Words](../../../)


