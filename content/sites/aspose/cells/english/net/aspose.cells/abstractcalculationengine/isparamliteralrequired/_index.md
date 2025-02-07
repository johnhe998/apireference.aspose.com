---
title: AbstractCalculationEngine.IsParamLiteralRequired
second_title: Aspose.Cells for .NET API Reference
description: AbstractCalculationEngine property. Indicates whether this engine needs the literal text of parameter while doing calculation. Default value is false
type: docs
url: /net/aspose.cells/abstractcalculationengine/isparamliteralrequired/
---
## AbstractCalculationEngine.IsParamLiteralRequired property

Indicates whether this engine needs the literal text of parameter while doing calculation. Default value is false.

```csharp
public virtual bool IsParamLiteralRequired { get; }
```

### Remarks

If this custom calculation engine requires the parameter's literal text, more stacks will be required to cache the literal text for parameters and Calculate() method may be called recursively to calculate the parameter's value. Commonly the literal text is not needed for calculating formulas and this method should return false for most implementations to get better performance.

### See Also

* class [AbstractCalculationEngine](../)
* namespace [Aspose.Cells](../../../aspose.cells/)
* assembly [Aspose.Cells](../../../)


