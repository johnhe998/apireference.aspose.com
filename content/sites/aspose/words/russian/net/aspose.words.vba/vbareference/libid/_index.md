---
title: VbaReference.LibId
second_title: Справочник по API Aspose.Words для .NET
description: VbaReference свойство. Получает строковое значение содержащее идентификатор библиотеки типов автоматизации.
type: docs
weight: 10
url: /ru/net/aspose.words.vba/vbareference/libid/
---
## VbaReference.LibId property

Получает строковое значение, содержащее идентификатор библиотеки типов автоматизации.

```csharp
public abstract string LibId { get; }
```

### Примечания

В зависимости от типа ссылки значение этого свойства может быть:

* ссылка на LibidReference, указанная в 2.1.1.8.
* ProjectReference, указанный в 2.1.1.12 ProjectReference [MS-OVBA]: https://docs.microsoft.com/en-us/openspecs/office_file_formats/ms-ovba/9a45ac1a-f1ff-4ebd-958e-537701aa8131

### Примеры

Показывает, как получить/удалить элемент из коллекции ссылок VBA.

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
/// Возвращает строку, представляющую путь LibId указанной ссылки. 
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
/// Возвращает путь из указанного идентификатора библиотеки типов автоматизации.
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
/// Возвращает путь из указанного идентификатора библиотеки типов автоматизации.
/// </summary>
private static string GetLibIdProjectPath(string libIdProject)
{
    return libIdProject != null ? libIdProject.Substring(3) : "";
}
```

### Смотрите также

* class [VbaReference](../)
* пространство имен [Aspose.Words.Vba](../../vbareference/)
* сборка [Aspose.Words](../../../)


