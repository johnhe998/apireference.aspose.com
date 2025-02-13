---
title: Metered.GetConsumptionQuantity
second_title: Aspose.Words för .NET API Referens
description: Metered metod. Får förbrukningsfilstorlek
type: docs
weight: 40
url: /sv/net/aspose.words/metered/getconsumptionquantity/
---
## Metered.GetConsumptionQuantity method

Får förbrukningsfilstorlek

```csharp
public static decimal GetConsumptionQuantity()
```

### Returvärde

konsumtionsmängd

### Exempel

Visar hur du aktiverar en mätlicens och spårar kredit/förbrukning.

```csharp
// Skapa en ny Metered-licens och skriv sedan ut dess användningsstatistik.
Metered metered = new Metered();
metered.SetMeteredKey("MyPublicKey", "MyPrivateKey");

Console.WriteLine($"Credit before operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity before operation: {Metered.GetConsumptionQuantity()}");

// Använd Aspose.Words och skriv sedan ut vår mätstatistik igen för att se hur mycket vi spenderade.
Document doc = new Document(MyDir + "Document.docx");
doc.Save(ArtifactsDir + "Metered.Usage.pdf");

// Aspose Metered Licensing-mekanism skickar inte användningsdata till köpservern varje gång,
// du måste använda väntande.
System.Threading.Thread.Sleep(10000);

Console.WriteLine($"Credit after operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity after operation: {Metered.GetConsumptionQuantity()}");
```

### Se även

* class [Metered](../)
* namnutrymme [Aspose.Words](../../metered/)
* hopsättning [Aspose.Words](../../../)


