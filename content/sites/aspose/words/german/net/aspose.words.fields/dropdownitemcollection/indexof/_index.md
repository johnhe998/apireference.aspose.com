---
title: DropDownItemCollection.IndexOf
second_title: Aspose.Words für .NET-API-Referenz
description: DropDownItemCollection methode. Gibt den nullbasierten Index des angegebenen Werts in der Sammlung zurück.
type: docs
weight: 70
url: /de/net/aspose.words.fields/dropdownitemcollection/indexof/
---
## DropDownItemCollection.IndexOf method

Gibt den nullbasierten Index des angegebenen Werts in der Sammlung zurück.

```csharp
public int IndexOf(string value)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| value | String | Der zu suchende Wert, bei dem die Groß-/Kleinschreibung beachtet werden soll. |

### Rückgabewert

Der nullbasierte Index. Negativer Wert, wenn nicht gefunden.

### Beispiele

Zeigt, wie ein Kombinationsfeldfeld eingefügt und die Elemente in seiner Elementauflistung bearbeitet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Kombinationsfeld ein und überprüfen Sie dann seine Sammlung von Dropdown-Elementen.
// In Microsoft Word klickt der Benutzer auf das Kombinationsfeld,
// und wählen Sie dann eines der anzuzeigenden Textelemente in der Sammlung aus.
string[] items = { "One", "Two", "Three" };
FormField comboBoxField = builder.InsertComboBox("DropDown", items, 0);
DropDownItemCollection dropDownItems = comboBoxField.DropDownItems;

Assert.AreEqual(3, dropDownItems.Count);
Assert.AreEqual("One", dropDownItems[0]);
Assert.AreEqual(1, dropDownItems.IndexOf("Two"));
Assert.IsTrue(dropDownItems.Contains("Three"));

// Es gibt zwei Möglichkeiten, ein neues Element zu einer bestehenden Sammlung von Dropdown-Box-Elementen hinzuzufügen.
// 1 - Ein Element an das Ende der Sammlung anhängen:
dropDownItems.Add("Four");

// 2 - Ein Element vor einem anderen Element an einem angegebenen Index einfügen:
dropDownItems.Insert(3, "Three and a half");

Assert.AreEqual(5, dropDownItems.Count);

// Iteriere über die Sammlung und drucke jedes Element.
using (IEnumerator<string> dropDownCollectionEnumerator = dropDownItems.GetEnumerator())
    while (dropDownCollectionEnumerator.MoveNext())
        Console.WriteLine(dropDownCollectionEnumerator.Current);

// Es gibt zwei Möglichkeiten, Elemente aus einer Sammlung von Dropdown-Elementen zu entfernen.
// 1 - Entferne ein Element, dessen Inhalt dem übergebenen String entspricht:
dropDownItems.Remove("Four");

// 2 - Entfernen Sie ein Element an einem Index:
dropDownItems.RemoveAt(3);

Assert.AreEqual(3, dropDownItems.Count);
Assert.IsFalse(dropDownItems.Contains("Three and a half"));
Assert.IsFalse(dropDownItems.Contains("Four"));

doc.Save(ArtifactsDir + "FormFields.DropDownItemCollection.html");

// Die gesamte Sammlung von Dropdown-Elementen leeren.
dropDownItems.Clear();
```

### Siehe auch

* class [DropDownItemCollection](../)
* namensraum [Aspose.Words.Fields](../../dropdownitemcollection/)
* Montage [Aspose.Words](../../../)


