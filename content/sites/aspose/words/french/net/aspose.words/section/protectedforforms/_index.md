---
title: Section.ProtectedForForms
second_title: Référence de l'API Aspose.Words pour .NET
description: Section propriété. Vrai si la section est protégée pour les formulaires. Lorsquune section est protégée pour les formulaires les utilisateurs peuvent sélectionner et modifier du texte uniquement dans les champs de formulaire de Microsoft Word.
type: docs
weight: 60
url: /fr/net/aspose.words/section/protectedforforms/
---
## Section.ProtectedForForms property

Vrai si la section est protégée pour les formulaires. Lorsqu'une section est protégée pour les formulaires, les utilisateurs peuvent sélectionner et modifier du texte uniquement dans les champs de formulaire de Microsoft Word.

```csharp
public bool ProtectedForForms { get; set; }
```

### Exemples

Montre comment désactiver la protection d'une section.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Section 1. Hello world!");
builder.InsertBreak(BreakType.SectionBreakNewPage);

builder.Writeln("Section 2. Hello again!");
builder.Write("Please enter text here: ");
builder.InsertTextInput("TextInput1", TextFormFieldType.Regular, "", "Placeholder text", 0);

// Appliquez la protection en écriture à chaque section du document.
doc.Protect(ProtectionType.AllowOnlyFormFields);

// Désactiver la protection en écriture pour la première section.
doc.Sections[0].ProtectedForForms = false;

// Dans ce document de sortie, nous pourrons éditer librement la première section,
// et nous ne pourrons modifier que le contenu du champ du formulaire dans la deuxième section.
doc.Save(ArtifactsDir + "Section.Protect.docx");
```

### Voir également

* class [Section](../)
* espace de noms [Aspose.Words](../../section/)
* Assemblée [Aspose.Words](../../../)


