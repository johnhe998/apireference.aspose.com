---
title: Class OdsoRecipientData
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Settings.OdsoRecipientData klass. Representerar information om en enskild post inom en extern datakälla som ska uteslutas från kopplingen.
type: docs
weight: 5630
url: /sv/net/aspose.words.settings/odsorecipientdata/
---
## OdsoRecipientData class

Representerar information om en enskild post inom en extern datakälla som ska uteslutas från kopplingen.

```csharp
public class OdsoRecipientData
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [OdsoRecipientData](odsorecipientdata/)() | Default_Constructor |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Active](../../aspose.words.settings/odsorecipientdata/active/) { get; set; } | Anger om posten från datakällan ska importeras till ett dokument när sammanslagningen utförs. Standardvärdet är`Sann` . |
| [Column](../../aspose.words.settings/odsorecipientdata/column/) { get; set; } | Anger kolumnen i datakällan som innehåller unika data för den aktuella posten. Standardvärdet är 0. |
| [Hash](../../aspose.words.settings/odsorecipientdata/hash/) { get; set; } | Representerar hashkoden för denna post. Ibland använder Microsoft Word[`Hash`](./hash/) av en hel skiva istället för en[`UniqueTag`](./uniquetag/) value. Standardvärdet är 0. |
| [UniqueTag](../../aspose.words.settings/odsorecipientdata/uniquetag/) { get; set; } | Anger innehållet i en given post i kolumnen som innehåller unika data. Standardvärdet är`null` . |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [Clone](../../aspose.words.settings/odsorecipientdata/clone/)() | Returnerar en djup klon av detta objekt. |

### Anmärkningar

Om en post ska slås samman till en sammanfogad handling, behövs ingen information om den posten. Men om en given post inte ska slås samman till ett sammanfogat dokument, ska värdet på den unika nyckeln för den posten lagras i[`UniqueTag`](./uniquetag/) egenskapen för detta objekt för att indikera detta undantag.

### Exempel

Visar hur man får åtkomst till insamlingen av data som anger vilka sammanslagningsdatakällaposter en sammanslagning kommer att utesluta.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

OdsoRecipientDataCollection dataCollection = doc.MailMergeSettings.Odso.RecipientDatas;

Assert.AreEqual(70, dataCollection.Count);

using (IEnumerator<OdsoRecipientData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine(
            $"Odso recipient data index {index++} will {(enumerator.Current.Active ? "" : "not ")}be imported upon mail merge.");
        Console.WriteLine($"\tColumn #{enumerator.Current.Column}");
        Console.WriteLine($"\tHash code: {enumerator.Current.Hash}");
        Console.WriteLine($"\tContents array length: {enumerator.Current.UniqueTag.Length}");
    }
}

// Vi kan klona elementen i den här samlingen.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Vi kan också ta bort element individuellt, eller rensa hela samlingen på en gång.
dataCollection.RemoveAt(0);

Assert.AreEqual(69, dataCollection.Count);

dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Se även

* namnutrymme [Aspose.Words.Settings](../../aspose.words.settings/)
* hopsättning [Aspose.Words](../../)


