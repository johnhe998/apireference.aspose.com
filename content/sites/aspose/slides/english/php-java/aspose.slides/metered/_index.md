---
title: Metered
second_title: Aspose.Sildes for Node.js via Java API Reference
description: 
type: docs

url: /node-java/aspose.slides/metered/
---

## Metered class
Provides methods to set metered key.

## Functions

| Name | Description |
| --- | --- |
| [Metered](metered)() | Initializes a new instance of this class. |

## Functions

| Name | Description |
| --- | --- |
| [getConsumptionCredit](getconsumptioncredit)() | Gets consumption credit |
| [getConsumptionQuantity](getconsumptionquantity)() | Gets consumption file size |
| [setMeteredKey](setmeteredkey)(String, String) | Sets metered public and private key. If you purchase metered license, when start application, this API should be called, normally, this is enough. However, if always fail to upload consumption data and exceed 24 hours, the license will be set to evaluation status, to avoid such case, you should regularly check the license status, if it is evaluation status, call this API again. |
