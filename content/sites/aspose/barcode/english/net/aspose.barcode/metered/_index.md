---
title: Class Metered
second_title: Aspose.BarCode for .NET API Reference
description: Aspose.BarCode.Metered class. Provides methods to set metered key
type: docs
weight: 1380
url: /net/aspose.barcode/metered/
---
## Metered class

Provides methods to set metered key.

```csharp
public class Metered
```

## Constructors

| Name | Description |
| --- | --- |
| [Metered](metered/)() | The default constructor. |

## Methods

| Name | Description |
| --- | --- |
| [SetMeteredKey](../../aspose.barcode/metered/setmeteredkey/)(string, string) | Sets metered public and private key |
| static [GetConsumptionCredit](../../aspose.barcode/metered/getconsumptioncredit/)() | Gets consumption credit |
| static [GetConsumptionQuantity](../../aspose.barcode/metered/getconsumptionquantity/)() | Gets consumption file size |

## Examples

In this example, an attempt will be made to set metered public and private key

```csharp
[C#]

Metered matered = new Metered();
matered.SetMeteredKey("PublicKey", "PrivateKey");


[Visual Basic]

Dim matered As Metered = New Metered
matered.SetMeteredKey("PublicKey", "PrivateKey")
```

### See Also

* namespace [Aspose.BarCode](../../aspose.barcode/)
* assembly [Aspose.BarCode](../../)


