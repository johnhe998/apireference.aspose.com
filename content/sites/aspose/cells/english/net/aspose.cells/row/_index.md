---
title: Class Row
second_title: Aspose.Cells for .NET API Reference
description: Aspose.Cells.Row class. Represents a single row in a worksheet
type: docs
url: /net/aspose.cells/row/
---
## Row class

Represents a single row in a worksheet.

```csharp
public class Row : IEnumerable
```

## Properties

| Name | Description |
| --- | --- |
| [FirstCell](../../aspose.cells/row/firstcell/) { get; } | Gets the first cell object in the row. |
| [FirstDataCell](../../aspose.cells/row/firstdatacell/) { get; } | Gets the first non-blank cell in the row. |
| [GroupLevel](../../aspose.cells/row/grouplevel/) { get; set; } | Gets the group level of the row. |
| [HasCustomStyle](../../aspose.cells/row/hascustomstyle/) { get; } | Indicates whether this row has custom style settings(different from the default one inherited from workbook). |
| [Height](../../aspose.cells/row/height/) { get; set; } | Gets and sets the row height in unit of Points. |
| [Index](../../aspose.cells/row/index/) { get; } | Gets the index of this row. |
| [IsBlank](../../aspose.cells/row/isblank/) { get; } | Indicates whether the row contains any data |
| [IsCollapsed](../../aspose.cells/row/iscollapsed/) { get; set; } | whether the row is collapsed |
| [IsHeightMatched](../../aspose.cells/row/isheightmatched/) { get; set; } | Indicates that row height and default font height matches. |
| [IsHidden](../../aspose.cells/row/ishidden/) { get; set; } | Indicates whether the row is hidden. |
| [Item](../../aspose.cells/row/item/) { get; } | Gets the cell. |
| [LastCell](../../aspose.cells/row/lastcell/) { get; } | Gets the last cell object in the row. |
| [LastDataCell](../../aspose.cells/row/lastdatacell/) { get; } | Gets the last non-blank cell in the row. |
| [Style](../../aspose.cells/row/style/) { get; } | (**Obsolete.**) Represents the style of this row. |

## Methods

| Name | Description |
| --- | --- |
| [ApplyStyle](../../aspose.cells/row/applystyle/)(Style, StyleFlag) | Applies formats for a whole row. |
| [CopySettings](../../aspose.cells/row/copysettings/)(Row, bool) | Copy settings of row, such as style, height, visibility, ...etc. |
| override [Equals](../../aspose.cells/row/equals/#equals_1)(object) | Checks whether this object refers to the same row with another. |
| [Equals](../../aspose.cells/row/equals/#equals)(Row) | Checks whether this object refers to the same row with another row object. |
| [GetCellByIndex](../../aspose.cells/row/getcellbyindex/)(int) | (**Obsolete.**) Get the cell by specific index in the list. |
| [GetCellOrNull](../../aspose.cells/row/getcellornull/)(int) | Gets the cell or null in the specific index. |
| [GetEnumerator](../../aspose.cells/row/getenumerator/#getenumerator)() | Gets the cells enumerator |
| [GetEnumerator](../../aspose.cells/row/getenumerator/#getenumerator_1)(bool, bool) | Gets an enumerator that iterates cells through this row. |
| [GetStyle](../../aspose.cells/row/getstyle/)() | Gets the style of this row. |
| [SetStyle](../../aspose.cells/row/setstyle/)(Style) | Sets the style of this row. |

### Examples

```csharp

[C#]

//Instantiating a Workbook object
Workbook workbook = new Workbook();

//Obtaining the reference of the first worksheet
Worksheet worksheet = workbook.Worksheets[0];
Style style = workbook.CreateStyle();

//Setting the background color to Blue
style.BackgroundColor = Color.Blue;

//Setting the foreground color to Red
style.ForegroundColor= Color.Red;

//setting Background Pattern
style.Pattern = BackgroundType.DiagonalStripe;

//New Style Flag
StyleFlag styleFlag = new StyleFlag();

//Set All Styles
styleFlag.All = true;

 //Get first row
Row row = worksheet.Cells.Rows[0];
 //Apply Style to first row
row.ApplyStyle(style, styleFlag);

//Saving the Excel file
workbook.Save("book1.xls");

[VB.NET]

'Instantiating a Workbook object
Dim workbook As Workbook = New Workbook()

'Obtaining the reference of the first worksheet
Dim worksheet As Worksheet = workbook.Worksheets(0)

Dim style As Style = workbook.CreateStyle()

'Setting the background color to Blue
style.BackgroundColor = Color.Blue

'Setting the foreground color to Red
style.ForegroundColor = Color.Red

'setting Background Pattern
style.Pattern = BackgroundType.DiagonalStripe

'New Style Flag
Dim styleFlag As New StyleFlag()

'Set All Styles
styleFlag.All = True

 'Get first row
Dim row as Row = worksheet.Cells.Rows(0)
 'Apply Style to first row
row.ApplyStyle(style, styleFlag)

'Saving the Excel file
workbook.Save("book1.xls")
```

### See Also

* namespace [Aspose.Cells](../../aspose.cells/)
* assembly [Aspose.Cells](../../)


