---
title: Class VbaReferenceCollection
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Vba.VbaReferenceCollection classe. Représente une collection deVbaReference objets.
type: docs
weight: 6290
url: /fr/net/aspose.words.vba/vbareferencecollection/
---
## VbaReferenceCollection class

Représente une collection de[`VbaReference`](../vbareference/) objets.

```csharp
public sealed class VbaReferenceCollection : IEnumerable<VbaReference>
```

## Propriétés

| Nom | La description |
| --- | --- |
| [Count](../../aspose.words.vba/vbareferencecollection/count/) { get; } | Renvoie le nombre de références VBA dans la collection. |
| [Item](../../aspose.words.vba/vbareferencecollection/item/) { get; } | Obtient[`VbaReference`](../vbareference/) objet à l'index spécifié. |

## Méthodes

| Nom | La description |
| --- | --- |
| [Remove](../../aspose.words.vba/vbareferencecollection/remove/)(VbaReference) | Supprime la première occurrence d'un élément VbaReference spécifié de la collection. |
| [RemoveAt](../../aspose.words.vba/vbareferencecollection/removeat/)(int) | Supprime l'élément VbaReference à l'index spécifié de la collection. |

### Exemples

Montre comment obtenir/supprimer un élément de la collection de référence VBA.

```csharp
[Test]
public void RemoveVbaReference()
{
    const string brokenPath = @"X:\broken.dll";
    Document doc = new Document(MyDir + "VBA project.docm");

    VbaReferenceCollection references = doc.VbaProject.References;
    Assert.AreEqual(5 ,references.Count);

    for (int i = references.Count - 1; i >= 0; i--)
    {
        VbaReference reference = doc.VbaProject.References[i];
        string path = GetLibIdPath(reference);

        if (path == brokenPath)
            references.RemoveAt(i);
    }
    Assert.AreEqual(4 ,references.Count);

    references.Remove(references[1]);
    Assert.AreEqual(3 ,references.Count);

    doc.Save(ArtifactsDir + "VbaProject.RemoveVbaReference.docm"); 
}

/// <summary>
/// Renvoie une chaîne représentant le chemin LibId d'une référence spécifiée. 
/// </summary>
private static string GetLibIdPath(VbaReference reference)
{
    switch (reference.Type)
    {
        case VbaReferenceType.Registered:
        case VbaReferenceType.Original:
        case VbaReferenceType.Control:
            return GetLibIdReferencePath(reference.LibId);
        case VbaReferenceType.Project:
            return GetLibIdProjectPath(reference.LibId);
        default:
            throw new ArgumentOutOfRangeException();
    }
}

/// <summary>
/// Renvoie le chemin à partir d'un identifiant spécifié d'une bibliothèque de types Automation.
/// </summary>
private static string GetLibIdReferencePath(string libIdReference)
{
    if (libIdReference != null)
    {
        string[] refParts = libIdReference.Split('#');
        if (refParts.Length > 3)
            return refParts[3];
    }

    return "";
}

/// <summary>
/// Renvoie le chemin à partir d'un identifiant spécifié d'une bibliothèque de types Automation.
/// </summary>
private static string GetLibIdProjectPath(string libIdProject)
{
    return libIdProject != null ? libIdProject.Substring(3) : "";
}
```

### Voir également

* class [VbaReference](../vbareference/)
* espace de noms [Aspose.Words.Vba](../../aspose.words.vba/)
* Assemblée [Aspose.Words](../../)


