---
title: Class CustomXmlSchemaCollection
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Markup.CustomXmlSchemaCollection klas. Eine Sammlung von Zeichenfolgen die XMLSchemas darstellen die einem benutzerdefinierten XMLTeil zugeordnet sind.
type: docs
weight: 3720
url: /de/net/aspose.words.markup/customxmlschemacollection/
---
## CustomXmlSchemaCollection class

Eine Sammlung von Zeichenfolgen, die XML-Schemas darstellen, die einem benutzerdefinierten XML-Teil zugeordnet sind.

```csharp
public class CustomXmlSchemaCollection : IEnumerable<string>
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Count](../../aspose.words.markup/customxmlschemacollection/count/) { get; } | Ruft die Anzahl der in der Sammlung enthaltenen Elemente ab. |
| [Item](../../aspose.words.markup/customxmlschemacollection/item/) { get; set; } | Ruft das Element am angegebenen Index ab oder legt es fest. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Add](../../aspose.words.markup/customxmlschemacollection/add/)(string) | Fügt der Sammlung ein Element hinzu. |
| [Clear](../../aspose.words.markup/customxmlschemacollection/clear/)() | Entfernt alle Elemente aus der Sammlung. |
| [Clone](../../aspose.words.markup/customxmlschemacollection/clone/)() | Erstellt einen tiefen Klon dieses Objekts. |
| [GetEnumerator](../../aspose.words.markup/customxmlschemacollection/getenumerator/)() | Gibt ein Aufzählungsobjekt zurück, das verwendet werden kann, um alle Elemente in der Sammlung zu durchlaufen. |
| [IndexOf](../../aspose.words.markup/customxmlschemacollection/indexof/)(string) | Gibt den nullbasierten Index des angegebenen Werts in der Sammlung zurück. |
| [Remove](../../aspose.words.markup/customxmlschemacollection/remove/)(string) | Entfernt den angegebenen Wert aus der Sammlung. |
| [RemoveAt](../../aspose.words.markup/customxmlschemacollection/removeat/)(int) | Entfernt einen Wert am angegebenen Index. |

### Bemerkungen

Sie erstellen keine Instanzen dieser Klasse. Sie greifen auf die Sammlung von XML-Schemas eines benutzerdefinierten XML-Teils über die zu[`Schemas`](../customxmlpart/schemas/) Eigentum.

### Beispiele

Zeigt, wie mit einer XML-Schemaauflistung gearbeitet wird.

```csharp
Document doc = new Document();

string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello, World!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

// Eine XML-Schemazuordnung hinzufügen.
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema");

// Klonen Sie die XML-Schemazuordnungssammlung des benutzerdefinierten XML-Teils,
// und fügen Sie dem Klon dann ein paar neue Schemas hinzu.
CustomXmlSchemaCollection schemas = xmlPart.Schemas.Clone();
schemas.Add("http://www.w3.org/2001/XMLSchema-Instanz");
schemas.Add("http://schemas.microsoft.com/office/2006/metadata/contentType");

Assert.AreEqual(3, schemas.Count);
Assert.AreEqual(2, schemas.IndexOf("http://schemas.microsoft.com/office/2006/metadata/contentType"));

// Die Schemas aufzählen und jedes Element drucken.
using (IEnumerator<string> enumerator = schemas.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine(enumerator.Current);
}

// Im Folgenden finden Sie drei Möglichkeiten zum Entfernen von Schemas aus der Sammlung.
// 1 - Entfernen Sie ein Schema nach Index:
schemas.RemoveAt(2);

// 2 - Schema nach Wert entfernen:
schemas.Remove("http://www.w3.org/2001/XMLSchema");

// 3 - Verwenden Sie die "Clear"-Methode, um die Sammlung sofort zu leeren.
schemas.Clear();

Assert.AreEqual(0, schemas.Count);
```

### Siehe auch

* namensraum [Aspose.Words.Markup](../../aspose.words.markup/)
* Montage [Aspose.Words](../../)


