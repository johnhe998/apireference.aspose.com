---
title: Class Metered
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Metered klas. Bietet Methoden zum Festlegen von gemessenen Schlüsseln.
type: docs
weight: 3920
url: /de/net/aspose.words/metered/
---
## Metered class

Bietet Methoden zum Festlegen von gemessenen Schlüsseln.

```csharp
public class Metered
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [Metered](metered/)() | Initialisiert eine neue Instanz dieser Klasse. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [SetMeteredKey](../../aspose.words/metered/setmeteredkey/)(string, string) | Legt den gemessenen öffentlichen und privaten Schlüssel fest. Wenn Sie eine gemessene Lizenz erwerben, sollte beim Start der Anwendung diese API aufgerufen werden, normalerweise reicht dies aus. Wenn es jedoch immer fehlschlägt, Verbrauchsdaten hochzuladen und 24 Stunden überschreiten, wird die Lizenz auf den Evaluierungsstatus gesetzt, um einen solchen Fall zu vermeiden, sollten Sie den Lizenzstatus regelmäßig überprüfen. Wenn es sich um einen Evaluierungsstatus handelt, rufen Sie diese API erneut auf. |
| static [GetConsumptionCredit](../../aspose.words/metered/getconsumptioncredit/)() | erhält Verbrauchsguthaben |
| static [GetConsumptionQuantity](../../aspose.words/metered/getconsumptionquantity/)() | Ruft die Verbrauchsdateigröße ab |

### Beispiele

In diesem Beispiel wird versucht, einen getakteten öffentlichen und privaten Schlüssel festzulegen

```csharp
[C#]

Metered matered = new Metered();
matered.SetMeteredKey("PublicKey", "PrivateKey");


[Visual Basic]

Dim matered As Metered = New Metered
matered.SetMeteredKey("PublicKey", "PrivateKey")
```

Zeigt, wie eine kostenpflichtige Lizenz aktiviert und Guthaben/Verbrauch nachverfolgt wird.

```csharp
// Erstellen Sie eine neue Metered-Lizenz und drucken Sie dann ihre Nutzungsstatistiken.
Metered metered = new Metered();
metered.SetMeteredKey("MyPublicKey", "MyPrivateKey");

Console.WriteLine($"Credit before operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity before operation: {Metered.GetConsumptionQuantity()}");

// Arbeiten Sie mit Aspose.Words und drucken Sie dann unsere gemessenen Statistiken erneut aus, um zu sehen, wie viel wir ausgegeben haben.
Document doc = new Document(MyDir + "Document.docx");
doc.Save(ArtifactsDir + "Metered.Usage.pdf");

// Der Aspose Metered Licensing-Mechanismus sendet die Nutzungsdaten nicht jedes Mal an den Kaufserver,
// Sie müssen warten verwenden.
System.Threading.Thread.Sleep(10000);

Console.WriteLine($"Credit after operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity after operation: {Metered.GetConsumptionQuantity()}");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


