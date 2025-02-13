---
title: Class Metered
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Metered classe. Fournit des méthodes pour définir la clé mesurée.
type: docs
weight: 3920
url: /fr/net/aspose.words/metered/
---
## Metered class

Fournit des méthodes pour définir la clé mesurée.

```csharp
public class Metered
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [Metered](metered/)() | Initialise une nouvelle instance de cette classe. |

## Méthodes

| Nom | La description |
| --- | --- |
| [SetMeteredKey](../../aspose.words/metered/setmeteredkey/)(string, string) | Définit la clé publique et privée mesurée. Si vous achetez une licence mesurée, lorsque vous démarrez l'application, cette API doit être appelée, normalement, cela suffit. Cependant, si vous ne parvenez toujours pas à télécharger les données de consommation et dépassez 24 heures, la licence sera définie sur le statut d'évaluation, pour éviter ce cas, vous devez vérifier régulièrement le statut de la licence, s'il s'agit du statut d'évaluation, appelez à nouveau cette API. |
| static [GetConsumptionCredit](../../aspose.words/metered/getconsumptioncredit/)() | Obtient un crédit de consommation |
| static [GetConsumptionQuantity](../../aspose.words/metered/getconsumptionquantity/)() | Obtient la taille du fichier de consommation |

### Exemples

Dans cet exemple, une tentative sera faite pour définir des clés publiques et privées mesurées

```csharp
[C#]

Metered matered = new Metered();
matered.SetMeteredKey("PublicKey", "PrivateKey");


[Visual Basic]

Dim matered As Metered = New Metered
matered.SetMeteredKey("PublicKey", "PrivateKey")
```

Montre comment activer une licence au compteur et suivre le crédit/la consommation.

```csharp
// Créez une nouvelle licence avec compteur, puis imprimez ses statistiques d'utilisation.
Metered metered = new Metered();
metered.SetMeteredKey("MyPublicKey", "MyPrivateKey");

Console.WriteLine($"Credit before operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity before operation: {Metered.GetConsumptionQuantity()}");

// Opérez en utilisant Aspose.Words, puis imprimez à nouveau nos statistiques mesurées pour voir combien nous avons dépensé.
Document doc = new Document(MyDir + "Document.docx");
doc.Save(ArtifactsDir + "Metered.Usage.pdf");

// Le mécanisme Aspose Metered Licensing n'envoie pas les données d'utilisation au serveur d'achat à chaque fois,
// vous devez utiliser l'attente.
System.Threading.Thread.Sleep(10000);

Console.WriteLine($"Credit after operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity after operation: {Metered.GetConsumptionQuantity()}");
```

### Voir également

* espace de noms [Aspose.Words](../../aspose.words/)
* Assemblée [Aspose.Words](../../)


