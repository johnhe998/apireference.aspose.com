---
title: DocumentBuilder.InsertBreak
second_title: Référence de l'API Aspose.Words pour .NET
description: DocumentBuilder méthode. Insère une rupture du type spécifié dans le document.
type: docs
weight: 240
url: /fr/net/aspose.words/documentbuilder/insertbreak/
---
## DocumentBuilder.InsertBreak method

Insère une rupture du type spécifié dans le document.

```csharp
public void InsertBreak(BreakType breakType)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| breakType | BreakType | Spécifie le type de saut à insérer. |

### Remarques

Utilisez cette méthode pour insérer un paragraphe, une page, une colonne, une section ou un saut de ligne dans le document.

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

Montre comment appliquer et rétablir les paramètres de mise en page aux sections d'un document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Modifie les propriétés de mise en page pour la section actuelle du générateur et ajoute du texte.
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.VerticalAlignment = PageVerticalAlignment.Center;
builder.Writeln("This is the first section, which landscape oriented with vertically centered text.");

// Si nous commençons une nouvelle section en utilisant un générateur de document,
// il héritera des propriétés de configuration de page actuelles du générateur.
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(Orientation.Landscape, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Center, doc.Sections[1].PageSetup.VerticalAlignment);

// Nous pouvons rétablir ses propriétés de mise en page à leurs valeurs par défaut en utilisant la méthode "ClearFormatting".
builder.PageSetup.ClearFormatting();

Assert.AreEqual(Orientation.Portrait, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Top, doc.Sections[1].PageSetup.VerticalAlignment);

builder.Writeln("This is the second section, which is in default Letter paper size, portrait orientation and top alignment.");

doc.Save(ArtifactsDir + "PageSetup.ClearFormatting.docx");
```

Montre comment insérer une table des matières (TOC) dans un document en utilisant des styles de titre comme entrées.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère une table des matières pour la première page du document.
// Configurer le tableau pour récupérer les paragraphes avec des titres de niveaux 1 à 3.
// De plus, définissez ses entrées comme étant des hyperliens qui nous mèneront
// à l'emplacement de l'en-tête lors d'un clic gauche dans Microsoft Word.
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// Remplir la table des matières en ajoutant des paragraphes avec des styles de titre.
// Chacun de ces titres avec un niveau compris entre 1 et 3 créera une entrée dans la table.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;
builder.Writeln("Heading 3.1.3.1");
builder.Writeln("Heading 3.1.3.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");

// Une table des matières est un champ d'un type qui doit être mis à jour pour afficher un résultat à jour.
doc.UpdateFields();
doc.Save(ArtifactsDir + "DocumentBuilder.InsertToc.docx");
```

### Voir également

* enum [BreakType](../../breaktype/)
* class [DocumentBuilder](../)
* espace de noms [Aspose.Words](../../documentbuilder/)
* Assemblée [Aspose.Words](../../../)


