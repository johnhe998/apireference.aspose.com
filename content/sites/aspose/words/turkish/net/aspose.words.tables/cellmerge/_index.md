---
title: Enum CellMerge
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Tables.CellMerge Sıralama. Tablodaki bir hücrenin diğer hücrelerle nasıl birleştirileceğini belirtir.
type: docs
weight: 5970
url: /tr/net/aspose.words.tables/cellmerge/
---
## CellMerge enumeration

Tablodaki bir hücrenin diğer hücrelerle nasıl birleştirileceğini belirtir.

```csharp
public enum CellMerge
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Hücre birleştirilmemiş. |
| First | `1` | Hücre, birleştirilmiş hücre aralığındaki ilk hücredir. |
| Previous | `2` | Hücre, önceki hücreyle yatay veya dikey olarak birleştirilir. |

### Örnekler

Tablo hücrelerinin yatay olarak nasıl birleştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İlk satırın ilk sütununa bir hücre ekleyin.
// Bu hücre, yatay olarak birleştirilmiş hücre aralığındaki ilk hücre olacaktır.
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// İlk satırın ikinci sütununa bir hücre ekleyin. Metin içeriği eklemek yerine,
// bu hücreyi doğrudan sola eklediğimiz ilk hücre ile birleştireceğiz.
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();

// İkinci satıra birleştirilmemiş iki hücre daha ekleyin.
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.InsertCell();
builder.Write("Text in unmerged cell.");
builder.InsertCell();
builder.Write("Text in unmerged cell.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "CellFormat.HorizontalMerge.docx");
```

Bir hücrenin yatay ve dikey birleştirme türünü yazdırır.

```csharp
public void CheckCellsMerged()
{
    Document doc = new Document(MyDir + "Table with merged cells.docx");
    Table table = doc.FirstSection.Body.Tables[0];

    foreach (Row row in table.Rows.OfType<Row>())
        foreach (Cell cell in row.Cells.OfType<Cell>())
            Console.WriteLine(PrintCellMergeType(cell));
}

public string PrintCellMergeType(Cell cell)
{
    bool isHorizontallyMerged = cell.CellFormat.HorizontalMerge != CellMerge.None;
    bool isVerticallyMerged = cell.CellFormat.VerticalMerge != CellMerge.None;
    string cellLocation =
        $"R{cell.ParentRow.ParentTable.IndexOf(cell.ParentRow) + 1}, C{cell.ParentRow.IndexOf(cell) + 1}";

    if (isHorizontallyMerged && isVerticallyMerged)
        return $"The cell at {cellLocation} is both horizontally and vertically merged";
    if (isHorizontallyMerged)
        return $"The cell at {cellLocation} is horizontally merged.";

    return isVerticallyMerged ? $"The cell at {cellLocation} is vertically merged" : $"The cell at {cellLocation} is not merged";
}
```

Tablo hücrelerinin dikey olarak nasıl birleştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İlk satırın ilk sütununa bir hücre ekleyin.
// Bu hücre, dikey olarak birleştirilmiş hücre aralığındaki ilk hücre olacaktır.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// İlk satırın ikinci sütununa bir hücre ekleyin, ardından satırı bitirin.
// Ayrıca, oluşturucuyu oluşturulan hücrelerde dikey birleştirmeyi devre dışı bırakacak şekilde yapılandırın.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();

// İkinci satırın ilk sütununa bir hücre ekleyin. 
// Metin içeriği eklemek yerine, bu hücreyi doğrudan yukarıda eklediğimiz ilk hücreyle birleştireceğiz.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// İkinci satırın ikinci sütununa başka bir bağımsız hücre ekle.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "CellFormat.VerticalMerge.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Tables](../../aspose.words.tables/)
* toplantı [Aspose.Words](../../)


