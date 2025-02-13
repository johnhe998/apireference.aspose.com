---
title: Metered.SetMeteredKey
second_title: Aspose.Words per .NET API Reference
description: Metered metodo. Imposta la chiave pubblica e privata misurata. Se acquisti una licenza misurata quando avvii lapplicazione questa API dovrebbe essere chiamata normalmente questo è sufficiente. Tuttavia se il caricamento dei dati di consumo non riesce sempre e supera le 24 ore la licenza verrà impostata sullo stato di valutazione per evitare questo caso è necessario controllare regolarmente lo stato della licenza se è lo stato di valutazione richiamare questa API.
type: docs
weight: 20
url: /it/net/aspose.words/metered/setmeteredkey/
---
## Metered.SetMeteredKey method

Imposta la chiave pubblica e privata misurata. Se acquisti una licenza misurata, quando avvii l'applicazione, questa API dovrebbe essere chiamata, normalmente, questo è sufficiente. Tuttavia, se il caricamento dei dati di consumo non riesce sempre e supera le 24 ore, la licenza verrà impostata sullo stato di valutazione, per evitare questo caso, è necessario controllare regolarmente lo stato della licenza, se è lo stato di valutazione, richiamare questa API.

```csharp
public void SetMeteredKey(string publicKey, string privateKey)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| publicKey | String | chiave pubblica |
| privateKey | String | chiave privata |

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


