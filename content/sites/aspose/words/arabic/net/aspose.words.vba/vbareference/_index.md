---
title: Class VbaReference
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Vba.VbaReference فصل. تنفيذ مرجع إلى مكتبة نوع التنفيذ أو مشروع VBA.
type: docs
weight: 6280
url: /ar/net/aspose.words.vba/vbareference/
---
## VbaReference class

تنفيذ مرجع إلى مكتبة نوع التنفيذ أو مشروع VBA.

```csharp
public abstract class VbaReference
```

## الخصائص

| اسم | وصف |
| --- | --- |
| abstract [LibId](../../aspose.words.vba/vbareference/libid/) { get; } | يحصل على قيمة سلسلة تحتوي على معرف مكتبة نوع التنفيذ. |
| abstract [Type](../../aspose.words.vba/vbareference/type/) { get; } | يحصل[`VbaReferenceType`](../vbareferencetype/)كائن يشير إلى نوع المرجع الذي يمثله كائن VbaReference. |

### أمثلة

يوضح كيفية الحصول على / إزالة عنصر من مجموعة مرجع VBA.

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
/// إرجاع سلسلة تمثل مسار LibId لمرجع محدد. 
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
/// إرجاع المسار من معرف محدد لمكتبة نوع التنفيذ التلقائي.
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
/// إرجاع المسار من معرف محدد لمكتبة نوع التنفيذ التلقائي.
/// </summary>
private static string GetLibIdProjectPath(string libIdProject)
{
    return libIdProject != null ? libIdProject.Substring(3) : "";
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Vba](../../aspose.words.vba/)
* المجسم [Aspose.Words](../../)


