---
title: FieldAutoNum.SeparatorCharacter
second_title: Aspose.Words für .NET-API-Referenz
description: FieldAutoNum eigendom. Ruft das zu verwendende Trennzeichen ab oder setzt es.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldautonum/separatorcharacter/
---
## FieldAutoNum.SeparatorCharacter property

Ruft das zu verwendende Trennzeichen ab oder setzt es.

```csharp
public string SeparatorCharacter { get; set; }
```

### Beispiele

Zeigt, wie Absätze mithilfe von Autonum-Feldern nummeriert werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Jedes AUTONUM-Feld zeigt den aktuellen Wert einer laufenden Zählung von AUTONUM-Feldern an,
// ermöglicht es uns, Elemente wie eine nummerierte Liste automatisch zu nummerieren.
// Dieses Feld zeigt eine Zahl "1." an.
FieldAutoNum field = (FieldAutoNum)builder.InsertField(FieldType.FieldAutoNum, true);
builder.Writeln("\tParagraph 1.");

Assert.AreEqual(" AUTONUM ", field.GetFieldCode());

field = (FieldAutoNum)builder.InsertField(FieldType.FieldAutoNum, true);
builder.Writeln("\tParagraph 2.");

// Das Trennzeichen, das im Feldergebnis unmittelbar nach der Zahl erscheint, ist standardmäßig ein Punkt.
// Wenn wir diese Eigenschaft null lassen, zeigt unser zweites AUTONUM-Feld "2" an. im Dokument.
Assert.IsNull(field.SeparatorCharacter);

// Wir können diese Eigenschaft so einstellen, dass das erste Zeichen ihrer Zeichenfolge als neues Trennzeichen verwendet wird.
// In diesem Fall zeigt unser AUTONUM-Feld jetzt "2:" an.
field.SeparatorCharacter = ":";

Assert.AreEqual(" AUTONUM  \\s :", field.GetFieldCode());

doc.Save(ArtifactsDir + "Field.AUTONUM.docx");
```

### Siehe auch

* class [FieldAutoNum](../)
* namensraum [Aspose.Words.Fields](../../fieldautonum/)
* Montage [Aspose.Words](../../../)


