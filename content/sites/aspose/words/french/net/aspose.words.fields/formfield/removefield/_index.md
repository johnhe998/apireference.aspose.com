---
title: FormField.RemoveField
second_title: Référence de l'API Aspose.Words pour .NET
description: FormField méthode. Supprime le champ de formulaire complet pas seulement le caractère spécial du champ de formulaire.
type: docs
weight: 240
url: /fr/net/aspose.words.fields/formfield/removefield/
---
## FormField.RemoveField method

Supprime le champ de formulaire complet, pas seulement le caractère spécial du champ de formulaire.

```csharp
public void RemoveField()
```

### Remarques

Si un signet est associé au champ de formulaire, le signet n'est pas supprimé.

### Exemples

Montre comment supprimer un champ de formulaire.

```csharp
Document doc = new Document(MyDir + "Form fields.docx");

FormField formField = doc.Range.FormFields[3];
formField.RemoveField();
```

### Voir également

* class [FormField](../)
* espace de noms [Aspose.Words.Fields](../../formfield/)
* Assemblée [Aspose.Words](../../../)


