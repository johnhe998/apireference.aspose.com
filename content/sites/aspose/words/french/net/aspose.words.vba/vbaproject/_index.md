---
title: Class VbaProject
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Vba.VbaProject classe. Fournit un accès aux informations du projet VBA. Un projet VBA à lintérieur du document est défini comme une collection de modules VBA.
type: docs
weight: 6270
url: /fr/net/aspose.words.vba/vbaproject/
---
## VbaProject class

Fournit un accès aux informations du projet VBA. Un projet VBA à l'intérieur du document est défini comme une collection de modules VBA.

```csharp
public class VbaProject
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [VbaProject](vbaproject/)() | Crée un VbaProject vide. |

## Propriétés

| Nom | La description |
| --- | --- |
| [CodePage](../../aspose.words.vba/vbaproject/codepage/) { get; } | Renvoie la page de code du projet VBA. |
| [IsSigned](../../aspose.words.vba/vbaproject/issigned/) { get; } | Indique si le VbaProject est signé ou non. |
| [Modules](../../aspose.words.vba/vbaproject/modules/) { get; } | Renvoie la collection de modules de projet VBA. |
| [Name](../../aspose.words.vba/vbaproject/name/) { get; set; } | Obtient ou définit le nom du projet VBA. |
| [References](../../aspose.words.vba/vbaproject/references/) { get; } | Obtient une collection de références de projet VBA. |

## Méthodes

| Nom | La description |
| --- | --- |
| [Clone](../../aspose.words.vba/vbaproject/clone/)() | Effectue une copie du`VbaProject` . |

### Exemples

Montre comment accéder aux informations de projet VBA d'un document.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");

// Un projet VBA contient une collection de modules VBA.
VbaProject vbaProject = doc.VbaProject;
    ? $"Project name: {vbaProject.Name} signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n"
    : $"Project name: {vbaProject.Name} not signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n");

VbaModuleCollection vbaModules = doc.VbaProject.Modules; 

Assert.AreEqual(vbaModules.Count(), 3);

foreach (VbaModule module in vbaModules)
    Console.WriteLine($"Module name: {module.Name};\nModule code:\n{module.SourceCode}\n");

// Définit le nouveau code source pour le module VBA. Vous pouvez accéder aux modules VBA de la collection par index ou par nom.
vbaModules[0].SourceCode = "Your VBA code...";
vbaModules["Module1"].SourceCode = "Your VBA code...";

// Supprime un module de la collection.
vbaModules.Remove(vbaModules[2]);
```

### Voir également

* espace de noms [Aspose.Words.Vba](../../aspose.words.vba/)
* Assemblée [Aspose.Words](../../)


