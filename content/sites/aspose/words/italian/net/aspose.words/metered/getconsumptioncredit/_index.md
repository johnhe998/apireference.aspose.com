---
title: Metered.GetConsumptionCredit
second_title: Aspose.Words per .NET API Reference
description: Metered metodo. Ottiene credito di consumo
type: docs
weight: 30
url: /it/net/aspose.words/metered/getconsumptioncredit/
---
## Metered.GetConsumptionCredit method

Ottiene credito di consumo

```csharp
public static decimal GetConsumptionCredit()
```

### Valore di ritorno

quantità di consumo

### Esempi

Mostra come attivare una licenza Metered e tenere traccia del credito/consumo.

```csharp
// Crea una nuova licenza a consumo, quindi stampa le sue statistiche di utilizzo.
Metered metered = new Metered();
metered.SetMeteredKey("MyPublicKey", "MyPrivateKey");

Console.WriteLine($"Credit before operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity before operation: {Metered.GetConsumptionQuantity()}");

// Opera usando Aspose.Words, quindi stampa di nuovo le nostre statistiche misurate per vedere quanto abbiamo speso.
Document doc = new Document(MyDir + "Document.docx");
doc.Save(ArtifactsDir + "Metered.Usage.pdf");

// Il meccanismo di Aspose Metered Licensing non invia i dati di utilizzo al server di acquisto ogni volta,
// devi usare wait.
System.Threading.Thread.Sleep(10000);

Console.WriteLine($"Credit after operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity after operation: {Metered.GetConsumptionQuantity()}");
```

### Guarda anche

* class [Metered](../)
* spazio dei nomi [Aspose.Words](../../metered/)
* assemblea [Aspose.Words](../../../)


