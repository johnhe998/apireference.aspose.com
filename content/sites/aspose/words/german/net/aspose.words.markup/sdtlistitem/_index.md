---
title: Class SdtListItem
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Markup.SdtListItem klas. Dieses Element gibt ein einzelnes Listenelement innerhalb eines übergeordneten Elements anComboBox oderDropDownList strukturiertes DokumentTag.
type: docs
weight: 3780
url: /de/net/aspose.words.markup/sdtlistitem/
---
## SdtListItem class

Dieses Element gibt ein einzelnes Listenelement innerhalb eines übergeordneten Elements anComboBox oderDropDownList strukturiertes Dokument-Tag.

```csharp
public class SdtListItem
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [SdtListItem](sdtlistitem/#constructor)(string) | Initialisiert eine neue Instanz dieser Klasse. |
| [SdtListItem](sdtlistitem/#constructor_1)(string, string) | Initialisiert eine neue Instanz dieser Klasse. |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [DisplayText](../../aspose.words.markup/sdtlistitem/displaytext/) { get; } | Ruft den Text ab, der im Ausführungsinhalt anstelle von angezeigt werden soll[`Value`](./value/) Attributinhalte für dieses Listenelement. |
| [Value](../../aspose.words.markup/sdtlistitem/value/) { get; } | Ruft den Wert dieses Listenelements ab. |

### Beispiele

Zeigt, wie mit Dropdown-Listen-strukturierten Dokument-Tags gearbeitet wird.

```csharp
Document doc = new Document();
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.DropDownList, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(tag);

// Ein strukturiertes Dokument-Tag mit Dropdown-Liste ist ein Formular, das dem Benutzer dies ermöglicht
// Wählen Sie eine Option aus einer Liste aus, indem Sie mit der linken Maustaste klicken und das Formular in Microsoft Word öffnen.
// Die Eigenschaft "ListItems" enthält alle Listenelemente, und jedes Listenelement ist ein "SdtListItem".
SdtListItemCollection listItems = tag.ListItems;
listItems.Add(new SdtListItem("Value 1"));

Assert.AreEqual(listItems[0].DisplayText, listItems[0].Value);

// Drei weitere Listenelemente hinzufügen. Initialisieren Sie diese Elemente mit einem anderen Konstruktor als das erste Element
// um Strings anzuzeigen, die sich von ihren Werten unterscheiden.
listItems.Add(new SdtListItem("Item 2", "Value 2"));
listItems.Add(new SdtListItem("Item 3", "Value 3"));
listItems.Add(new SdtListItem("Item 4", "Value 4"));

Assert.AreEqual(4, listItems.Count);

// Die Dropdown-Liste zeigt das erste Element an. Weisen Sie dem "SelectedValue" einen anderen Listeneintrag zu, um ihn anzuzeigen.
listItems.SelectedValue = listItems[3];

Assert.AreEqual("Value 4", listItems.SelectedValue.Value);

// Auflistung über die Sammlung und jedes Element drucken.
using (IEnumerator<SdtListItem> enumerator = listItems.GetEnumerator())
{
    while (enumerator.MoveNext())
        if (enumerator.Current != null)
            Console.WriteLine($"List item: {enumerator.Current.DisplayText}, value: {enumerator.Current.Value}");
}

 // Das letzte Listenelement entfernen.
listItems.RemoveAt(3);

Assert.AreEqual(3, listItems.Count);

// Da unser Dropdown-Steuerelement standardmäßig so eingestellt ist, dass es das entfernte Element anzeigt, geben Sie ihm ein Element zum Anzeigen, das vorhanden ist.
listItems.SelectedValue = listItems[1];

doc.Save(ArtifactsDir + "StructuredDocumentTag.ListItemCollection.docx");

// Verwenden Sie die "Clear"-Methode, um die gesamte Dropdown-Elementsammlung auf einmal zu leeren.
listItems.Clear();

Assert.AreEqual(0, listItems.Count);
```

### Siehe auch

* namensraum [Aspose.Words.Markup](../../aspose.words.markup/)
* Montage [Aspose.Words](../../)


