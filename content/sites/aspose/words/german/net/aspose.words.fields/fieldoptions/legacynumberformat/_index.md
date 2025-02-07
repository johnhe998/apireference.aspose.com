---
title: FieldOptions.LegacyNumberFormat
second_title: Aspose.Words für .NET-API-Referenz
description: FieldOptions eigendom. Ruft den Wert ab oder legt ihn fest der angibt ob das LegacyZahlenformat vor AW 13.10 für Felder aktiviert ist oder nicht.
type: docs
weight: 140
url: /de/net/aspose.words.fields/fieldoptions/legacynumberformat/
---
## FieldOptions.LegacyNumberFormat property

Ruft den Wert ab oder legt ihn fest, der angibt, ob das Legacy-Zahlenformat (vor AW 13.10) für Felder aktiviert ist oder nicht.

```csharp
public bool LegacyNumberFormat { get; set; }
```

### Bemerkungen

Wenn diese Eigenschaft auf eingestellt ist **Stimmt**, Vorlagensymbol "#" funktionierte wie in .net: Ersetzt das Nummernzeichen durch die entsprechende Ziffer, falls vorhanden; andernfalls erscheinen keine Symbole in der Ergebniszeichenfolge.

Wenn diese Eigenschaft auf eingestellt ist **FALSCH**, Vorlagensymbol "#" funktioniert wie MS Word: Dieses Formatelement gibt die erforderlichen numerischen Stellen an, die im Ergebnis angezeigt werden sollen. Wenn das Ergebnis an dieser Stelle keine Ziffer enthält, zeigt MS Word ein Leerzeichen an. Beispiel: { = 9 + 6 \# $### } zeigt 15 $ an.

Der Standardwert ist **FALSCH**.

### Beispiele

Zeigt, wie die Legacy-Zahlenformatierung für Felder aktiviert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("= 2 + 3 \\# $##");

Assert.AreEqual("$ 5", field.Result);

doc.FieldOptions.LegacyNumberFormat = true;
field.Update();

Assert.AreEqual("$5", field.Result);
```

### Siehe auch

* class [FieldOptions](../)
* namensraum [Aspose.Words.Fields](../../fieldoptions/)
* Montage [Aspose.Words](../../../)


