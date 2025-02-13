---
title: Workbook.CalculateFormula
second_title: Aspose.Cells for .NET API Reference
description: Workbook method. Calculates the result of formulas
type: docs
url: /net/aspose.cells/workbook/calculateformula/
---
## CalculateFormula() {#calculateformula}

Calculates the result of formulas.

```csharp
public void CalculateFormula()
```

### Remarks

For all supported formulas, please see the list at https://docs.aspose.com/display/cellsnet/Supported+Formula+Functions

### See Also

* class [Workbook](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)

---

## CalculateFormula(bool) {#calculateformula_2}

Calculates the result of formulas.

```csharp
public void CalculateFormula(bool ignoreError)
```

| Parameter | Type | Description |
| --- | --- | --- |
| ignoreError | Boolean | Indicates if hide the error in calculating formulas. The error may be unsupported function, external links, etc. |

### See Also

* class [Workbook](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)

---

## CalculateFormula(bool, ICustomFunction) {#calculateformula_3}

Calculates the result of formulas.

```csharp
[Obsolete("Use CalculateFormula(CalculationOptions) method instead.")]
[EditorBrowsable(EditorBrowsableState.Never)]
public void CalculateFormula(bool ignoreError, ICustomFunction customFunction)
```

| Parameter | Type | Description |
| --- | --- | --- |
| ignoreError | Boolean | Indicates if hide the error in calculating formulas. The error may be unsupported function, external links, etc. |
| customFunction | ICustomFunction | The custom formula calculation functions to extend the calculation engine. |

### Remarks

NOTE: This member is now obsolete. Instead, please use CalculateFormula(CalculationOptions) method. This method will be removed 12 months later since August 2020. Aspose apologizes for any inconvenience you may have experienced.

### See Also

* interface [ICustomFunction](../../icustomfunction/)
* class [Workbook](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)

---

## CalculateFormula(CalculationOptions) {#calculateformula_1}

Calculating formulas in this workbook.

```csharp
public void CalculateFormula(CalculationOptions options)
```

| Parameter | Type | Description |
| --- | --- | --- |
| options | CalculationOptions | Options for calculation |

### See Also

* class [CalculationOptions](../../calculationoptions/)
* class [Workbook](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)


