---
title: WorkbookSettings.CalcStackSize
second_title: Aspose.Cells for .NET API Reference
description: WorkbookSettings property. Specifies the stack size for calculating cells recursively. The large value for this size will give better performance when there are lots of cells need to be calculated recursively. On the other hand larger value will raise the risk of StackOverflowException. If user gets StackOverflowException when calculating formulas this value should be decreased
type: docs
url: /net/aspose.cells/workbooksettings/calcstacksize/
---
## WorkbookSettings.CalcStackSize property

Specifies the stack size for calculating cells recursively. The large value for this size will give better performance when there are lots of cells need to be calculated recursively. On the other hand, larger value will raise the risk of StackOverflowException. If user gets StackOverflowException when calculating formulas, this value should be decreased.

```csharp
[Obsolete("Use CalculationOptions.CalcStackSize instead.")]
[EditorBrowsable(EditorBrowsableState.Never)]
public int CalcStackSize { get; set; }
```

### Remarks

NOTE: This member is now obsolete. Instead, please use CalculationOptions with the specified CalcStackSize when calculating formulas. This property will be removed 12 months later since February 2022. Aspose apologizes for any inconvenience you may have experienced.

### See Also

* class [WorkbookSettings](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)


