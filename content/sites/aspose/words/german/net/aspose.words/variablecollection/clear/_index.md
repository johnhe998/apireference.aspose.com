---
title: VariableCollection.Clear
second_title: Aspose.Words für .NET-API-Referenz
description: VariableCollection methode. Entfernt alle Elemente aus der Sammlung.
type: docs
weight: 40
url: /de/net/aspose.words/variablecollection/clear/
---
## VariableCollection.Clear method

Entfernt alle Elemente aus der Sammlung.

```csharp
public void Clear()
```

### Beispiele

Zeigt, wie mit der Variablensammlung eines Dokuments gearbeitet wird.

```csharp
Document doc = new Document();
VariableCollection variables = doc.Variables;

// Jedes Dokument hat eine Sammlung von Schlüssel/Wert-Paar-Variablen, denen wir Elemente hinzufügen können.
variables.Add("Home address", "123 Main St.");
variables.Add("City", "London");
variables.Add("Bedrooms", "3");

Assert.AreEqual(3, variables.Count);

// Wir können die Werte von Variablen im Dokumentkörper mithilfe von DOCVARIABLE-Feldern anzeigen.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocVariable field = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
field.VariableName = "Home address";
field.Update();

Assert.AreEqual("123 Main St.", field.Result);

// Durch Zuweisen von Werten zu vorhandenen Schlüsseln werden diese aktualisiert.
variables.Add("Home address", "456 Queen St.");

// Wir müssen dann DOCVARIABLE-Felder aktualisieren, um sicherzustellen, dass sie einen aktuellen Wert anzeigen.
Assert.AreEqual("123 Main St.", field.Result);

field.Update();

Assert.AreEqual("456 Queen St.", field.Result);

// Überprüfen Sie, ob die Dokumentvariablen mit einem bestimmten Namen oder Wert vorhanden sind.
Assert.True(variables.Contains("City"));
Assert.True(variables.Any(v => v.Value == "London"));

// Die Sammlung von Variablen sortiert Variablen automatisch alphabetisch nach Namen.
Assert.AreEqual(0, variables.IndexOfKey("Bedrooms"));
Assert.AreEqual(1, variables.IndexOfKey("City"));
Assert.AreEqual(2, variables.IndexOfKey("Home address"));

// Aufzählung über die Sammlung von Variablen.
using (IEnumerator<KeyValuePair<string, string>> enumerator = doc.Variables.GetEnumerator())
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: {enumerator.Current.Key}, Value: {enumerator.Current.Value}");

// Nachfolgend finden Sie drei Möglichkeiten, Dokumentvariablen aus einer Sammlung zu entfernen.
// 1 - Nach Namen:
variables.Remove("City");

Assert.False(variables.Contains("City"));

// 2 - Nach Index:
variables.RemoveAt(1);

Assert.False(variables.Contains("Home address"));

// 3 - Löschen Sie die gesamte Sammlung auf einmal:
variables.Clear();

Assert.That(variables, Is.Empty);
```

### Siehe auch

* class [VariableCollection](../)
* namensraum [Aspose.Words](../../variablecollection/)
* Montage [Aspose.Words](../../../)


