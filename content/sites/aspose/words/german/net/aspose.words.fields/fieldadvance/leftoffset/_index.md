---
title: FieldAdvance.LeftOffset
second_title: Aspose.Words für .NET-API-Referenz
description: FieldAdvance eigendom. Ermittelt oder setzt die Anzahl der Punkte um die der Text der dem Feld folgt nach links verschoben werden soll.
type: docs
weight: 40
url: /de/net/aspose.words.fields/fieldadvance/leftoffset/
---
## FieldAdvance.LeftOffset property

Ermittelt oder setzt die Anzahl der Punkte, um die der Text, der dem Feld folgt, nach links verschoben werden soll.

```csharp
public string LeftOffset { get; set; }
```

### Beispiele

Zeigt, wie ein ADVANCE-Feld eingefügt und seine Eigenschaften bearbeitet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("This text is in its normal place.");

// Im Folgenden finden Sie zwei Möglichkeiten, das ADVANCE-Feld zu verwenden, um die Position des darauf folgenden Textes anzupassen.
// Die Effekte eines ADVANCE-Feldes werden weiter angewendet, bis der Absatz endet,
// oder ein anderes ADVANCE-Feld aktualisiert die Versatz-/Koordinatenwerte.
// 1 - Geben Sie einen Richtungsoffset an:
FieldAdvance field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.RightOffset = "5";
field.UpOffset = "5";

Assert.AreEqual(" ADVANCE  \\r 5 \\u 5", field.GetFieldCode());

builder.Write("This text will be moved up and to the right.");

field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.DownOffset = "5";
field.LeftOffset = "100";

Assert.AreEqual(" ADVANCE  \\d 5 \\l 100", field.GetFieldCode());

builder.Writeln("This text is moved down and to the left, overlapping the previous text.");

// 2 - Text an eine durch Koordinaten angegebene Position verschieben:
field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.HorizontalPosition = "-100";
field.VerticalPosition = "200";

Assert.AreEqual(" ADVANCE  \\x -100 \\y 200", field.GetFieldCode());

builder.Write("This text is in a custom position.");

doc.Save(ArtifactsDir + "Field.ADVANCE.docx");
```

### Siehe auch

* class [FieldAdvance](../)
* namensraum [Aspose.Words.Fields](../../fieldadvance/)
* Montage [Aspose.Words](../../../)


