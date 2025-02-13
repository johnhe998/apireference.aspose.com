---
title: RtfLoadOptions.RecognizeUtf8Text
second_title: Aspose.Words för .NET API Referens
description: RtfLoadOptions fast egendom. När satt till santCharsetDetectorkommer att försöka upptäcka UTF8tecken de kommer att bevaras under import.
type: docs
weight: 20
url: /sv/net/aspose.words.loading/rtfloadoptions/recognizeutf8text/
---
## RtfLoadOptions.RecognizeUtf8Text property

När satt till sant,CharsetDetectorkommer att försöka upptäcka UTF8-tecken, de kommer att bevaras under import.

Standardvärdet är falskt.

```csharp
public bool RecognizeUtf8Text { get; set; }
```

### Exempel

Visar hur man upptäcker UTF-8-tecken när ett RTF-dokument laddas.

```csharp
// Skapa ett "RtfLoadOptions"-objekt för att ändra hur vi laddar ett RTF-dokument.
RtfLoadOptions loadOptions = new RtfLoadOptions();

// Ställ in egenskapen "RecognizeUtf8Text" till "false" för att anta att dokumentet använder ISO 8859-1-teckenuppsättningen
// och laddar varje tecken i dokumentet.
// Ställ in egenskapen "RecognizeUtf8Text" till "true" för att analysera alla tecken med variabel längd som kan förekomma i texten.
loadOptions.RecognizeUtf8Text = recognizeUtf8Text;

Document doc = new Document(MyDir + "UTF-8 characters.rtf", loadOptions);

Assert.AreEqual(
    recognizeUtf8Text
        ? "“John Doe´s list of currency symbols”™\r" +
          "€, ¢, £, ¥, ¤"
        : "â€œJohn DoeÂ´s list of currency symbolsâ€\u009dâ„¢\r" +
          "â‚¬, Â¢, Â£, Â¥, Â¤",
    doc.FirstSection.Body.GetText().Trim());
```

### Se även

* class [RtfLoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../rtfloadoptions/)
* hopsättning [Aspose.Words](../../../)


