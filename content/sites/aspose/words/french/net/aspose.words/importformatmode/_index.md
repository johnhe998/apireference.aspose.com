---
title: Enum ImportFormatMode
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.ImportFormatMode énumération. Spécifie comment le formatage est fusionné lors de limportation de contenu à partir dun autre document.
type: docs
weight: 3030
url: /fr/net/aspose.words/importformatmode/
---
## ImportFormatMode enumeration

Spécifie comment le formatage est fusionné lors de l'importation de contenu à partir d'un autre document.

```csharp
public enum ImportFormatMode
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| UseDestinationStyles | `0` | Utilisez les styles du document de destination et copiez les nouveaux styles. Il s'agit de l'option par défaut. |
| KeepSourceFormatting | `1` | Copiez tous les styles requis dans le document de destination, générez des noms de style uniques si nécessaire. |
| KeepDifferentStyles | `2` | Copiez uniquement les styles différents de ceux du document source. |

### Remarques

Lorsque vous copiez des nœuds d'un document à un autre, cette option spécifie comment formatting est résolu lorsque les deux documents ont un style avec le même nom, mais une mise en forme différente.

Le formatage est résolu comme suit :

1. Les styles intégrés sont mis en correspondance à l'aide de leur identifiant de style indépendant des paramètres régionaux. Les styles définis par l'utilisateur sont mis en correspondance à l'aide d'un nom de style sensible à la casse.
2. Si un style correspondant n'est pas trouvé dans le document de destination, le style (et tous les styles référencés par celui-ci) sont copiés dans le document de destination et les nœuds importés sont mis à jour pour référencer le nouveau style.
3. Si un style correspondant existe déjà dans le document de destination, ce qui se passe dépend du`importFormatModeimportFormatMode` paramètre passé à [`Document.ImportNodeDocument.ImportNode`](../documentbase/importnode/) comme décrit ci-dessous.

Lors de l'utilisation du **Utiliser les styles de destination** si un style correspondant existe déjà dans le document de destination, le style n'est pas copié et les nœuds importés sont mis à jour pour référencer le style existant.

L'inconvénient d'utiliser **Utiliser les styles de destination** est que le texte importé pourrait avoir un aspect différent dans le document de destination par rapport au document source. Par exemple, le style "Titre 1" dans le document source utilise la police Arial 16pt et le style "Titre 1" dans le document de destination utilise Times New Police Roman 14pt. Lors de l'importation de texte de style "Titre 1" sans autre mise en forme directe, il apparaîtra en tant que police Times New Roman 14pt dans le document de destination.

**KeepSourceFormatting**L'option permet de s'assurer que le contenu importé a le même aspect dans le document de destination que dans le document source. Si un style correspondant existe déjà dans le document de destination, la mise en forme du style source est développée dans les attributs de nœud directs et le style est changé en Normal. Si le style n'existe pas dans le document de destination, alors le style source est importé dans le document de destination et appliqué au nœud importé. Notez qu'il n'est pas toujours possible de conserver le style source même s'il n'existe pas dans le document de destination. Dans ce cas, la mise en forme d'un tel style sera étendue aux attributs de nœud directs en faveur de la préservation de la mise en forme originale du nœud.

L'inconvénient d'utiliser **KeepSourceFormatting**est que si vous effectuez plusieurs importations, vous pourriez vous retrouver avec de nombreux styles dans le document de destination et cela pourrait rendre difficile l'utilisation d'un formatage de style cohérent dans Microsoft Word pour ce document.

Utilisant **Conserverdifférentsstyles** L'option permet de réutiliser les styles de destination si la mise en forme qu'ils fournissent est identique aux styles du document source. Si le style du document de destination est différent de celui de la source, il est alors importé.

### Exemples

Montre comment insérer un document dans un autre document.

```csharp
Document doc = new Document(MyDir + "Document.docx");

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);

Document docToInsert = new Document(MyDir + "Formatted elements.docx");

builder.InsertDocument(docToInsert, ImportFormatMode.KeepSourceFormatting);
builder.Document.Save(ArtifactsDir + "DocumentBuilder.InsertDocument.docx");
```

### Voir également

* espace de noms [Aspose.Words](../../aspose.words/)
* Assemblée [Aspose.Words](../../)


