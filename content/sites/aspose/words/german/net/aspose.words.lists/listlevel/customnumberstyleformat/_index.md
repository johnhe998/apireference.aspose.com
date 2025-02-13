---
title: ListLevel.CustomNumberStyleFormat
second_title: Aspose.Words für .NET-API-Referenz
description: ListLevel eigendom. Ruft das benutzerdefinierte Zahlenstilformat für diese Listenebene ab. Zum Beispiel a ç ĝ ....
type: docs
weight: 20
url: /de/net/aspose.words.lists/listlevel/customnumberstyleformat/
---
## ListLevel.CustomNumberStyleFormat property

Ruft das benutzerdefinierte Zahlenstilformat für diese Listenebene ab. Zum Beispiel: "a, ç, ĝ, ...".

```csharp
public string CustomNumberStyleFormat { get; }
```

### Beispiele

Zeigt, wie das Format für eine Liste mit dem benutzerdefinierten Zahlenstil abgerufen wird.

```csharp
Document doc = new Document(MyDir + "List with leading zero.docx");

ListLevel listLevel = doc.FirstSection.Body.Paragraphs[0].ListFormat.ListLevel;

string customNumberStyleFormat = string.Empty;

if (listLevel.NumberStyle == NumberStyle.Custom)
    customNumberStyleFormat = listLevel.CustomNumberStyleFormat;

Assert.AreEqual("001, 002, 003, ...", customNumberStyleFormat);

// Wir können einen Wert für den angegebenen Index des Listenelements erhalten.
Assert.AreEqual("iv", ListLevel.GetEffectiveValue(4, NumberStyle.LowercaseRoman, null));
Assert.AreEqual("005", ListLevel.GetEffectiveValue(5, NumberStyle.Custom, customNumberStyleFormat));
```

### Siehe auch

* class [ListLevel](../)
* namensraum [Aspose.Words.Lists](../../listlevel/)
* Montage [Aspose.Words](../../../)


