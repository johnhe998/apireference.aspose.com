---
title: Enum VbaReferenceType
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Vba.VbaReferenceType uppräkning. Tillåter att ange typen av aVbaReference objekt.
type: docs
weight: 6300
url: /sv/net/aspose.words.vba/vbareferencetype/
---
## VbaReferenceType enumeration

Tillåter att ange typen av a[`VbaReference`](../vbareference/) objekt.

```csharp
public enum VbaReferenceType
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Registered | `13` | Anger en biblioteksreferenstyp för automatiseringstyp. |
| Project | `14` | Angav en extern VBA-projektreferenstyp. |
| Original | `51` | Anger en originalbiblioteksreferenstyp för automatiseringstyp. |
| Control | `47` | Anger en biblioteksreferenstyp med vridbar typ. |

### Exempel

Visar hur man hämtar/tar bort ett element från VBA-referenssamlingen.

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
/// Returnerar en sträng som representerar LibId-sökvägen för en angiven referens. 
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
/// Returnerar sökväg från en specificerad identifierare för ett bibliotek av automationstyp.
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
/// Returnerar sökväg från en specificerad identifierare för ett bibliotek av automationstyp.
/// </summary>
private static string GetLibIdProjectPath(string libIdProject)
{
    return libIdProject != null ? libIdProject.Substring(3) : "";
}
```

### Se även

* namnutrymme [Aspose.Words.Vba](../../aspose.words.vba/)
* hopsättning [Aspose.Words](../../)


