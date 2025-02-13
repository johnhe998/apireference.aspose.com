---
title: TxtLoadOptions.DetectNumberingWithWhitespaces
second_title: Aspose.Words für .NET-API-Referenz
description: TxtLoadOptions eigendom. Ermöglicht festzulegen wie nummerierte Listenelemente erkannt werden wenn ein Dokument aus dem NurTextFormat importiert wird. Der Standardwert ist wahr.
type: docs
weight: 20
url: /de/net/aspose.words.loading/txtloadoptions/detectnumberingwithwhitespaces/
---
## TxtLoadOptions.DetectNumberingWithWhitespaces property

Ermöglicht festzulegen, wie nummerierte Listenelemente erkannt werden, wenn ein Dokument aus dem Nur-Text-Format importiert wird. Der Standardwert ist wahr.

```csharp
public bool DetectNumberingWithWhitespaces { get; set; }
```

### Bemerkungen

Wenn diese Option auf "false" gesetzt ist, erkennt der Listenerkennungsalgorithmus Listenabsätze, wenn Listennummern mit enden, entweder Punkt, rechte Klammer oder Aufzählungszeichen (wie "•", "*", "-" oder "o").

Wenn diese Option auf „true“ gesetzt ist, werden Leerzeichen auch als Trennzeichen für Listennummern verwendet: Listenerkennungsalgorithmus für Nummerierung im arabischen Stil (1., 1.1.2.) verwendet sowohl Leerzeichen als auch Punktsymbole („.“).

### Beispiele

Zeigt, wie Listen beim Laden von Klartextdokumenten erkannt werden.

```csharp
// Erstellen Sie ein Klartextdokument in einer Zeichenfolge mit vier separaten Teilen, die wir als Listen interpretieren können,
// mit unterschiedlichen Trennzeichen. Beim Laden des Klartextdokuments in ein "Dokument"-Objekt,
// Aspose.Words erkennt immer die ersten drei Listen und fügt ein "List"-Objekt hinzu
// für jeden zur "Listen"-Eigenschaft des Dokuments.
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";

// Erstellen Sie ein "TxtLoadOptions"-Objekt, das wir an den Konstruktor eines Dokuments übergeben können
// um zu ändern, wie wir ein Klartextdokument laden.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Setzen Sie die Eigenschaft "DetectNumberingWithWhitespaces" auf "true", um nummerierte Elemente zu erkennen
// mit Whitespace-Trennzeichen, wie die vierte Liste in unserem Dokument, als Listen.
// Dies kann auch Absätze, die mit Zahlen beginnen, fälschlicherweise als Listen erkennen.
// Setzen Sie die Eigenschaft "DetectNumberingWithWhitespaces" auf "false"
// keine Listen aus nummerierten Elementen mit Leerzeichen als Trennzeichen erstellen.
loadOptions.DetectNumberingWithWhitespaces = detectNumberingWithWhitespaces;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

if (detectNumberingWithWhitespaces)
{
    Assert.AreEqual(4, doc.Lists.Count);
    Assert.True(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
else
{
    Assert.AreEqual(3, doc.Lists.Count);
    Assert.False(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
```

### Siehe auch

* class [TxtLoadOptions](../)
* namensraum [Aspose.Words.Loading](../../txtloadoptions/)
* Montage [Aspose.Words](../../../)


