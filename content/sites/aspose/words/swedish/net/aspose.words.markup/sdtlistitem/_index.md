---
title: Class SdtListItem
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Markup.SdtListItem klass. Detta element specificerar ett enda listobjekt inom en förälderComboBox ellerDropDownList strukturerad dokumenttagg.
type: docs
weight: 3780
url: /sv/net/aspose.words.markup/sdtlistitem/
---
## SdtListItem class

Detta element specificerar ett enda listobjekt inom en förälderComboBox ellerDropDownList strukturerad dokumenttagg.

```csharp
public class SdtListItem
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [SdtListItem](sdtlistitem/#constructor)(string) | Initierar en ny instans av den här klassen. |
| [SdtListItem](sdtlistitem/#constructor_1)(string, string) | Initierar en ny instans av den här klassen. |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [DisplayText](../../aspose.words.markup/sdtlistitem/displaytext/) { get; } | Får texten att visa i körningsinnehållet istället för[`Value`](./value/) attributinnehåll för detta listobjekt. |
| [Value](../../aspose.words.markup/sdtlistitem/value/) { get; } | Hämtar värdet av denna listpost. |

### Exempel

Visar hur man arbetar med strukturerade dokumenttaggar i listrutan.

```csharp
Document doc = new Document();
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.DropDownList, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(tag);

// En rullgardinslista med strukturerad dokumenttagg är ett formulär som låter användaren
// välj ett alternativ från en lista genom att vänsterklicka och öppna formuläret i Microsoft Word.
// Egenskapen "ListItems" innehåller alla listobjekt, och varje listobjekt är en "SdtListItem".
SdtListItemCollection listItems = tag.ListItems;
listItems.Add(new SdtListItem("Value 1"));

Assert.AreEqual(listItems[0].DisplayText, listItems[0].Value);

// Lägg till ytterligare 3 listobjekt. Initiera dessa objekt med en annan konstruktor än det första objektet
// för att visa strängar som skiljer sig från deras värden.
listItems.Add(new SdtListItem("Item 2", "Value 2"));
listItems.Add(new SdtListItem("Item 3", "Value 3"));
listItems.Add(new SdtListItem("Item 4", "Value 4"));

Assert.AreEqual(4, listItems.Count);

// Rullgardinslistan visar det första objektet. Tilldela ett annat listobjekt till "SelectedValue" för att visa det.
listItems.SelectedValue = listItems[3];

Assert.AreEqual("Value 4", listItems.SelectedValue.Value);

// Räkna upp över samlingen och skriv ut varje element.
using (IEnumerator<SdtListItem> enumerator = listItems.GetEnumerator())
{
    while (enumerator.MoveNext())
        if (enumerator.Current != null)
            Console.WriteLine($"List item: {enumerator.Current.DisplayText}, value: {enumerator.Current.Value}");
}

  // Ta bort det sista listobjektet.
listItems.RemoveAt(3);

Assert.AreEqual(3, listItems.Count);

// Eftersom vår rullgardinskontroll är inställd på att visa det borttagna objektet som standard, ge det ett objekt att visa som finns.
listItems.SelectedValue = listItems[1];

doc.Save(ArtifactsDir + "StructuredDocumentTag.ListItemCollection.docx");

// Använd "Rensa"-metoden för att tömma hela rullgardinsmenyn på en gång.
listItems.Clear();

Assert.AreEqual(0, listItems.Count);
```

### Se även

* namnutrymme [Aspose.Words.Markup](../../aspose.words.markup/)
* hopsättning [Aspose.Words](../../)


