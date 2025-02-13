---
title: Document.PackageCustomParts
second_title: Référence de l'API Aspose.Words pour .NET
description: Document propriété. Obtient ou définit la collection de parties personnalisées contenu arbitraire liées au package OOXML à laide de relations inconnues.
type: docs
weight: 290
url: /fr/net/aspose.words/document/packagecustomparts/
---
## Document.PackageCustomParts property

Obtient ou définit la collection de parties personnalisées (contenu arbitraire) liées au package OOXML à l'aide de "relations inconnues".

```csharp
public CustomPartCollection PackageCustomParts { get; set; }
```

### Remarques

Ne confondez pas ces parties personnalisées avec les données XML personnalisées. Si vous avez besoin d'accéder à des parties XML personnalisées, utilisez le[`CustomXmlParts`](../customxmlparts/) propriété.

Cette collection contient des parties OOXML dont le parent est le package OOXML et dont les cibles sont d'une "relation inconnue". Pour plus d'informations, voir[`CustomPart`](../../../aspose.words.markup/custompart/).

Aspose.Words charge et enregistre les parties personnalisées dans des documents OOXML uniquement.

Cette propriété ne peut être`nul`.

### Exemples

Montre comment accéder à la collection de parties personnalisées arbitraires d'un document.

```csharp
Document doc = new Document(MyDir + "Custom parts OOXML package.docx");

Assert.AreEqual(2, doc.PackageCustomParts.Count);

// Clone la deuxième partie, puis ajoute le clone à la collection.
CustomPart clonedPart = doc.PackageCustomParts[1].Clone();
doc.PackageCustomParts.Add(clonedPart);
Assert.AreEqual(3, doc.PackageCustomParts.Count);

// Énumère la collection et imprime chaque partie.
using (IEnumerator<CustomPart> enumerator = doc.PackageCustomParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Part index {index}:");
        Console.WriteLine($"\tName:\t\t\t\t{enumerator.Current.Name}");
        Console.WriteLine($"\tContent type:\t\t{enumerator.Current.ContentType}");
        Console.WriteLine($"\tRelationship type:\t{enumerator.Current.RelationshipType}");
        Console.WriteLine(enumerator.Current.IsExternal ?
            "\tSourced from outside the document" :
            $"\tStored within the document, length: {enumerator.Current.Data.Length} bytes");
        index++;
    }
}

// Nous pouvons supprimer des éléments de cette collection individuellement ou tous à la fois.
doc.PackageCustomParts.RemoveAt(2);

Assert.AreEqual(2, doc.PackageCustomParts.Count);

doc.PackageCustomParts.Clear();

Assert.AreEqual(0, doc.PackageCustomParts.Count);
```

### Voir également

* class [CustomPartCollection](../../../aspose.words.markup/custompartcollection/)
* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


