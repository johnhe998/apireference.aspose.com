---
title: Class VariableCollection
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.VariableCollection klass. En samling dokumentvariabler.
type: docs
weight: 6230
url: /sv/net/aspose.words/variablecollection/
---
## VariableCollection class

En samling dokumentvariabler.

```csharp
public class VariableCollection : IEnumerable<KeyValuePair<string, string>>
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Count](../../aspose.words/variablecollection/count/) { get; } | Hämtar antalet element som finns i samlingen. |
| [Item](../../aspose.words/variablecollection/item/) { get; set; } | Hämtar eller ställer in en dokumentvariabel med det skiftlägesokänsliga namnet. null-värden är inte tillåtna som höger sida av tilldelningen och kommer att ersättas av en tom sträng. (2 indexers) |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Add](../../aspose.words/variablecollection/add/)(string, string) | Lägger till en dokumentvariabel till samlingen. |
| [Clear](../../aspose.words/variablecollection/clear/)() | Tar bort alla element från samlingen. |
| [Contains](../../aspose.words/variablecollection/contains/)(string) | Bestämmer om samlingen innehåller en dokumentvariabel med det angivna namnet. |
| [GetEnumerator](../../aspose.words/variablecollection/getenumerator/)() | Returnerar ett uppräkningsobjekt som kan användas för att iterera över alla variabler i samlingen. |
| [IndexOfKey](../../aspose.words/variablecollection/indexofkey/)(string) | Returnerar det nollbaserade indexet för den angivna dokumentvariabeln i samlingen. |
| [Remove](../../aspose.words/variablecollection/remove/)(string) | Tar bort en dokumentvariabel med det angivna namnet från samlingen. |
| [RemoveAt](../../aspose.words/variablecollection/removeat/)(int) | Tar bort en dokumentvariabel vid det angivna indexet. |

### Anmärkningar

Variabelnamn och -värden är strängar.

Variabelnamn är skiftlägesokänsliga.

### Exempel

Visar hur man arbetar med ett dokuments variabelsamling.

```csharp
Document doc = new Document();
VariableCollection variables = doc.Variables;

// Varje dokument har en samling nyckel-/värdeparvariabler som vi kan lägga till objekt till.
variables.Add("Home address", "123 Main St.");
variables.Add("City", "London");
variables.Add("Bedrooms", "3");

Assert.AreEqual(3, variables.Count);

// Vi kan visa värdena för variabler i dokumentets brödtext med hjälp av DOCVARIABLE-fält.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocVariable field = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
field.VariableName = "Home address";
field.Update();

Assert.AreEqual("123 Main St.", field.Result);

// Att tilldela värden till befintliga nycklar kommer att uppdatera dem.
variables.Add("Home address", "456 Queen St.");

// Vi måste då uppdatera DOCVARIABLE-fält för att säkerställa att de visar ett aktuellt värde.
Assert.AreEqual("123 Main St.", field.Result);

field.Update();

Assert.AreEqual("456 Queen St.", field.Result);

// Verifiera att dokumentvariablerna med ett visst namn eller värde finns.
Assert.True(variables.Contains("City"));
Assert.True(variables.Any(v => v.Value == "London"));

// Samlingen av variabler sorterar automatiskt variabler alfabetiskt efter namn.
Assert.AreEqual(0, variables.IndexOfKey("Bedrooms"));
Assert.AreEqual(1, variables.IndexOfKey("City"));
Assert.AreEqual(2, variables.IndexOfKey("Home address"));

// Räkna upp över samlingen av variabler.
using (IEnumerator<KeyValuePair<string, string>> enumerator = doc.Variables.GetEnumerator())
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: {enumerator.Current.Key}, Value: {enumerator.Current.Value}");

// Nedan finns tre sätt att ta bort dokumentvariabler från en samling.
// 1 - Efter namn:
variables.Remove("City");

Assert.False(variables.Contains("City"));

// 2 - Efter index:
variables.RemoveAt(1);

Assert.False(variables.Contains("Home address"));

// 3 - Rensa hela samlingen på en gång:
variables.Clear();

Assert.That(variables, Is.Empty);
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


