---
title: Cell.Calculate
second_title: Aspose.Cells for .NET API Reference
description: Cell method. Calculates the formula of the cell
type: docs
url: /net/aspose.cells/cell/calculate/
---
## Calculate(CalculationOptions) {#calculate}

Calculates the formula of the cell.

```csharp
public void Calculate(CalculationOptions options)
```

| Parameter | Type | Description |
| --- | --- | --- |
| options | CalculationOptions | Options for calculation |

### See Also

* class [CalculationOptions](../../calculationoptions/)
* class [Cell](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)

---

## Calculate(bool, ICustomFunction) {#calculate_1}

Calculates the formula of the cell.

```csharp
[Obsolete("Use Calculate(CalculationOptions) method instead.")]
[EditorBrowsable(EditorBrowsableState.Never)]
public void Calculate(bool ignoreError, ICustomFunction customFunction)
```

| Parameter | Type | Description |
| --- | --- | --- |
| ignoreError | Boolean | Indicates if hide the error in calculating formulas. The error may be unsupported function, external links, etc. |
| customFunction | ICustomFunction | The custom formula calculation functions to extend the calculation engine. |

### Remarks

NOTE: This member is now obsolete. Instead, please use Calculate(CalculationOptions) method. This method will be removed 12 months later since August 2020. Aspose apologizes for any inconvenience you may have experienced.

### See Also

* interface [ICustomFunction](../../icustomfunction/)
* class [Cell](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)


