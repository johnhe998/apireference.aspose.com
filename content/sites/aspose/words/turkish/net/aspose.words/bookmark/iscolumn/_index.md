---
title: Bookmark.IsColumn
second_title: Aspose.Words for .NET API Referansı
description: Bookmark mülk. İade doğru bu yer imi bir tablo sütunu yer imi ise.
type: docs
weight: 40
url: /tr/net/aspose.words/bookmark/iscolumn/
---
## Bookmark.IsColumn property

İade **doğru** bu yer imi bir tablo sütunu yer imi ise.

```csharp
public bool IsColumn { get; }
```

### Örnekler

Tablo sütunu yer imleri hakkında nasıl bilgi alınacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Table column bookmarks.doc");

foreach (Bookmark bookmark in doc.Range.Bookmarks)
{
    // Bir yer imi bir tablonun sütunlarını kapsıyorsa, bu bir tablo sütunu yer imidir ve IsColumn bayrağı true olarak ayarlanır.
    Console.WriteLine($"Bookmark: {bookmark.Name}{(bookmark.IsColumn ? " (Column)" : "")}");
    if (bookmark.IsColumn)
    {
        if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row &&
            bookmark.FirstColumn < row.Cells.Count)
        {
            // Yer iminin çevrelediği ilk ve son sütunların içeriğini yazdırın.
            Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
            Console.WriteLine(row.Cells[bookmark.LastColumn].GetText().TrimEnd(ControlChar.CellChar));
        }
    }
}
```

### Ayrıca bakınız

* class [Bookmark](../)
* ad alanı [Aspose.Words](../../bookmark/)
* toplantı [Aspose.Words](../../../)


