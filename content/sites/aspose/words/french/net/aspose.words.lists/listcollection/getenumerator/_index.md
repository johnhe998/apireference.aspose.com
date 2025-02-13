---
title: ListCollection.GetEnumerator
second_title: Référence de l'API Aspose.Words pour .NET
description: ListCollection méthode. Obtient lobjet énumérateur qui énumérera les listes dans le document.
type: docs
weight: 60
url: /fr/net/aspose.words.lists/listcollection/getenumerator/
---
## ListCollection.GetEnumerator method

Obtient l'objet énumérateur qui énumérera les listes dans le document.

```csharp
public IEnumerator<List> GetEnumerator()
```

### Exemples

Montre comment créer un document avec un échantillon de toutes les listes d'un autre document.

```csharp
public void PrintOutAllLists()
{
    Document srcDoc = new Document(MyDir + "Rendering.docx");

    Document dstDoc = new Document();
    DocumentBuilder builder = new DocumentBuilder(dstDoc);

    foreach (List srcList in srcDoc.Lists)
    {
        List dstList = dstDoc.Lists.AddCopy(srcList);
        AddListSample(builder, dstList);
    }

    dstDoc.Save(ArtifactsDir + "Lists.PrintOutAllLists.docx");
}

private static void AddListSample(DocumentBuilder builder, List list)
{
    builder.Writeln("Sample formatting of list with ListId:" + list.ListId);
    builder.ListFormat.List = list;
    for (int i = 0; i < list.ListLevels.Count; i++)
    {
        builder.ListFormat.ListLevelNumber = i;
        builder.Writeln("Level " + i);
    }

    builder.ListFormat.RemoveNumbers();
    builder.Writeln();
}
```

### Voir également

* class [List](../../list/)
* class [ListCollection](../)
* espace de noms [Aspose.Words.Lists](../../listcollection/)
* Assemblée [Aspose.Words](../../../)


