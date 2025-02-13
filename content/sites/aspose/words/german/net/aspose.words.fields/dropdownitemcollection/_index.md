---
title: Class DropDownItemCollection
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Fields.DropDownItemCollection klas. Eine Sammlung von Zeichenfolgen die alle Elemente in einem DropdownFormularfeld darstellen.
type: docs
weight: 1350
url: /de/net/aspose.words.fields/dropdownitemcollection/
---
## DropDownItemCollection class

Eine Sammlung von Zeichenfolgen, die alle Elemente in einem Dropdown-Formularfeld darstellen.

```csharp
public class DropDownItemCollection : IEnumerable<string>
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Count](../../aspose.words.fields/dropdownitemcollection/count/) { get; } | Ruft die Anzahl der in der Sammlung enthaltenen Elemente ab. |
| [Item](../../aspose.words.fields/dropdownitemcollection/item/) { get; set; } | Ruft das Element am angegebenen Index ab oder legt es fest. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Add](../../aspose.words.fields/dropdownitemcollection/add/)(string) | Fügt eine Zeichenfolge am Ende der Sammlung hinzu. |
| [Clear](../../aspose.words.fields/dropdownitemcollection/clear/)() | Entfernt alle Elemente aus der Sammlung. |
| [Contains](../../aspose.words.fields/dropdownitemcollection/contains/)(string) | Bestimmt, ob die Sammlung den angegebenen Wert enthält. |
| [GetEnumerator](../../aspose.words.fields/dropdownitemcollection/getenumerator/)() | Gibt ein Aufzählungsobjekt zurück, das verwendet werden kann, um alle Elemente in der Sammlung zu durchlaufen. |
| [IndexOf](../../aspose.words.fields/dropdownitemcollection/indexof/)(string) | Gibt den nullbasierten Index des angegebenen Werts in der Sammlung zurück. |
| [Insert](../../aspose.words.fields/dropdownitemcollection/insert/)(int, string) | Fügt eine Zeichenfolge am angegebenen Index in die Sammlung ein. |
| [Remove](../../aspose.words.fields/dropdownitemcollection/remove/)(string) | Entfernt den angegebenen Wert aus der Sammlung. |
| [RemoveAt](../../aspose.words.fields/dropdownitemcollection/removeat/)(int) | Entfernt einen Wert am angegebenen Index. |

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

* class [FormField](../formfield/)
* property [DropDownItems](../formfield/dropdownitems/)
* namensraum [Aspose.Words.Fields](../../aspose.words.fields/)
* Montage [Aspose.Words](../../)


