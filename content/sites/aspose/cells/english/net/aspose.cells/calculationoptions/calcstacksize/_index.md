---
title: CalculationOptions.CalcStackSize
second_title: Aspose.Cells for .NET API Reference
description: CalculationOptions property. Specifies the stack size for calculating cells recursively
type: docs
url: /net/aspose.cells/calculationoptions/calcstacksize/
---
## CalculationOptions.CalcStackSize property

Specifies the stack size for calculating cells recursively.

```csharp
public int CalcStackSize { get; set; }
```

### Remarks

When there are large amount of cells need to be calculated recursively in the dependency tree, StackOverflowException may be caused in the calculation process. If so, user should specify smaller value for this property. For such situation, user should determine the proper value for this property according to the actual formulas and data. Too small value may cause performance degradation for the formula calculation.

### See Also

* class [CalculationOptions](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)


