---
title: VbaReferenceCollection.Remove
second_title: Referencia de API de Aspose.Words para .NET
description: VbaReferenceCollection método. Elimina la primera aparición de un elemento VbaReference especificado de la colección.
type: docs
weight: 30
url: /es/net/aspose.words.vba/vbareferencecollection/remove/
---
## VbaReferenceCollection.Remove method

Elimina la primera aparición de un elemento VbaReference especificado de la colección.

```csharp
public void Remove(VbaReference item)
```

### Ejemplos

Muestra cómo obtener/eliminar un elemento de la colección de referencia de VBA.

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
/// Devuelve una cadena que representa la ruta LibId de una referencia especificada. 
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
/// Devuelve la ruta de un identificador especificado de una biblioteca de tipos de automatización.
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
/// Devuelve la ruta de un identificador especificado de una biblioteca de tipos de automatización.
/// </summary>
private static string GetLibIdProjectPath(string libIdProject)
{
    return libIdProject != null ? libIdProject.Substring(3) : "";
}
```

### Ver también

* class [VbaReference](../../vbareference/)
* class [VbaReferenceCollection](../)
* espacio de nombres [Aspose.Words.Vba](../../vbareferencecollection/)
* asamblea [Aspose.Words](../../../)


