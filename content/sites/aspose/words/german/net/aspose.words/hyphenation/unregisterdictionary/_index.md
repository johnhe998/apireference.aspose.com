---
title: Hyphenation.UnregisterDictionary
second_title: Aspose.Words für .NET-API-Referenz
description: Hyphenation methode. Deregistriert ein Silbentrennungswörterbuch für die angegebene Sprache.
type: docs
weight: 50
url: /de/net/aspose.words/hyphenation/unregisterdictionary/
---
## Hyphenation.UnregisterDictionary method

Deregistriert ein Silbentrennungswörterbuch für die angegebene Sprache.

Dies unterscheidet sich von der Registrierung des Null-Wörterbuchs. Das Aufheben der Registrierung eines Wörterbuchs aktiviert den Rückruf für die angegebene Sprache.

```csharp
public static void UnregisterDictionary(string language)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| language | String | Ein Sprachname, zB "en-US". Einzelheiten finden Sie in der .NET-Dokumentation für „Kulturname“ und RFC 4646. |

### Beispiele

Zeigt, wie ein Silbentrennungswörterbuch registriert wird.

```csharp
// Ein Silbentrennungswörterbuch enthält eine Liste von Strings, die Silbentrennungsregeln für die Sprache des Wörterbuchs definieren.
// Wenn ein Dokument Textzeilen enthält, in denen ein Wort aufgeteilt und in der nächsten Zeile fortgesetzt werden könnte,
// Die Silbentrennung durchsucht die Stringliste des Wörterbuchs nach den Teilstrings dieses Wortes.
// Wenn das Wörterbuch einen Teilstring enthält, wird das Wort durch Silbentrennung auf zwei Zeilen aufgeteilt
// durch den Teilstring und füge einen Bindestrich zur ersten Hälfte hinzu.
// Registrieren Sie eine Wörterbuchdatei aus dem lokalen Dateisystem für das Gebietsschema "de-CH".
Hyphenation.RegisterDictionary("de-CH", MyDir + "hyph_de_CH.dic");

Assert.True(Hyphenation.IsDictionaryRegistered("de-CH"));

// Öffnen Sie ein Dokument, das Text mit einem Gebietsschema enthält, das mit unserem Wörterbuch übereinstimmt,
// und in einem Festseiten-Speicherformat speichern. Der Text in diesem Dokument wird getrennt.
Document doc = new Document(MyDir + "German text.docx");

Assert.True(doc.FirstSection.Body.FirstParagraph.Runs.OfType<Run>().All(
    r => r.Font.LocaleId == new CultureInfo("de-CH").LCID));

doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Registered.pdf");

// Laden Sie das Dokument neu, nachdem Sie das Wörterbuch abgemeldet haben,
// und in einem anderen PDF speichern, das keinen getrennten Text enthält.
Hyphenation.UnregisterDictionary("de-CH");

Assert.False(Hyphenation.IsDictionaryRegistered("de-CH"));

doc = new Document(MyDir + "German text.docx");
doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Unregistered.pdf");
```

### Siehe auch

* class [Hyphenation](../)
* namensraum [Aspose.Words](../../hyphenation/)
* Montage [Aspose.Words](../../../)


