---
title: Spécifier la police par défaut lors du rendu
linktitle: Spécifier la police par défaut lors du rendu
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour spécifier la police par défaut lors du rendu d'un document à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/specify-default-font-when-rendering/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus de spécification de la police par défaut lors du rendu d'un document à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment spécifier une police par défaut à utiliser lors du rendu de vos documents à l'aide de Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document rendu modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document à afficher
 Ensuite, vous devez charger le document à rendre à l'aide de la`Document` classe. Assurez-vous de spécifier le bon chemin d'accès au document.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Définir la police par défaut
 Vous pouvez désormais spécifier la police par défaut à utiliser lors du rendu en créant une instance de`FontSettings` classe et la définition de la`DefaultFontName`propriété de la`DefaultFontSubstitution` s'opposer à la`DefaultFontSubstitution` objet`SubstitutionSettings` de`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Étape 4 : Enregistrer le document rendu
 Enfin, vous pouvez enregistrer le document rendu dans un fichier à l'aide de la`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Exemple de code source pour Spécifier la police par défaut lors du rendu à l'aide de Aspose.Words pour .NET 

```csharp
//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Si la police par défaut définie ici ne peut pas être trouvée lors du rendu, alors
// la police la plus proche sur la machine est utilisée à la place.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à spécifier la police par défaut lors du rendu d'un document à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement définir une police par défaut à utiliser lors du rendu de vos documents. Aspose.Words propose une API puissante et flexible pour le traitement de mots avec des polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser le rendu de vos documents en fonction de vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je spécifier une police par défaut lors de la conversion en PDF dans Aspose.Words ?

 R : Pour spécifier une police par défaut lors de la conversion en PDF dans Aspose.Words, vous pouvez utiliser le`PdfOptions`classe et définissez la`DefaultFontName` propriété au nom de la police souhaitée.

#### Q : Que se passe-t-il si la police par défaut n'est pas disponible lors de la conversion en PDF ?

R : Si la police par défaut spécifiée n'est pas disponible lors de la conversion en PDF, Aspose.Words utilisera une police de remplacement pour afficher le texte dans le document converti. Cela peut entraîner une légère différence d'apparence par rapport à la police d'origine.

#### Q : Puis-je spécifier une police par défaut pour d'autres formats de sortie, tels que DOCX ou HTML ?

: Oui, vous pouvez spécifier une police par défaut pour d'autres formats de sortie tels que DOCX ou HTML en utilisant les options de conversion appropriées et en définissant la propriété correspondante pour chaque format.

#### Q : Comment puis-je vérifier la police par défaut spécifiée dans Aspose.Words ?

 R : Pour vérifier la police par défaut spécifiée dans Aspose.Words, vous pouvez utiliser le`DefaultFontName`propriété de la`PdfOptions` class et récupère le nom de la police configurée.

#### Q : Est-il possible de spécifier une police par défaut différente pour chaque section du document ?

R : Oui, il est possible de spécifier une police par défaut différente pour chaque section du document à l'aide des options de formatage propres à chaque section. Cependant, cela nécessiterait une manipulation plus avancée du document à l'aide des fonctionnalités Aspose.Words.