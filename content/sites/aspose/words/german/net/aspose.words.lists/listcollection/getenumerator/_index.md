---
title: ListCollection.GetEnumerator
second_title: Aspose.Words für .NET-API-Referenz
description: ListCollection methode. Ruft das Aufzählungsobjekt ab das Listen im Dokument aufzählt.
type: docs
weight: 60
url: /de/net/aspose.words.lists/listcollection/getenumerator/
---
## ListCollection.GetEnumerator method

Ruft das Aufzählungsobjekt ab, das Listen im Dokument aufzählt.

```csharp
public IEnumerator<List> GetEnumerator()
```

### Beispiele

Zeigt, wie ein Dokument mit einem Beispiel aller Listen aus einem anderen Dokument erstellt wird.

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

### Siehe auch

* class [List](../../list/)
* class [ListCollection](../)
* namensraum [Aspose.Words.Lists](../../listcollection/)
* Montage [Aspose.Words](../../../)


