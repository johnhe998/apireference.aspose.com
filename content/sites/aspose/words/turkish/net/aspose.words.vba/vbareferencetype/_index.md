---
title: Enum VbaReferenceType
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Vba.VbaReferenceType Sıralama. BirVbaReference nesne.
type: docs
weight: 6300
url: /tr/net/aspose.words.vba/vbareferencetype/
---
## VbaReferenceType enumeration

Bir[`VbaReference`](../vbareference/) nesne.

```csharp
public enum VbaReferenceType
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Registered | `13` | Otomasyon türü kitaplığı başvuru türünü belirtir. |
| Project | `14` | Harici bir VBA projesi referans türü belirtildi. |
| Original | `51` | Özgün Otomasyon türü kitaplığı başvuru türünü belirtir. |
| Control | `47` | Döndürülmüş tür kitaplığı başvuru türünü belirtir. |

### Örnekler

VBA başvuru koleksiyonundan bir öğenin nasıl alınacağını/kaldırılacağını gösterir.

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
/// Belirtilen bir başvurunun LibId yolunu temsil eden dizeyi döndürür. 
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
/// Otomasyon türü kitaplığının belirtilen tanımlayıcısından yolu döndürür.
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
/// Otomasyon türü kitaplığının belirtilen tanımlayıcısından yolu döndürür.
/// </summary>
private static string GetLibIdProjectPath(string libIdProject)
{
    return libIdProject != null ? libIdProject.Substring(3) : "";
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Vba](../../aspose.words.vba/)
* toplantı [Aspose.Words](../../)


