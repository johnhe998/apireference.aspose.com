---
title: FieldPrint.PostScriptGroup
second_title: Aspose.Words für .NET-API-Referenz
description: FieldPrint eigendom. Ruft das Zeichenrechteck ab oder legt es fest auf dem die PostScriptAnweisungen arbeiten.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldprint/postscriptgroup/
---
## FieldPrint.PostScriptGroup property

Ruft das Zeichenrechteck ab oder legt es fest, auf dem die PostScript-Anweisungen arbeiten.

```csharp
public string PostScriptGroup { get; set; }
```

### Beispiele

Zeigt das Einfügen eines PRINT-Felds an.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("My paragraph");

// Das PRINT-Feld kann Anweisungen an den Drucker senden.
FieldPrint field = (FieldPrint)builder.InsertField(FieldType.FieldPrint, true);

// Legen Sie den Bereich fest, in dem der Drucker Anweisungen ausführen soll.
// In diesem Fall ist es der Absatz, der unser PRINT-Feld enthält.
field.PostScriptGroup = "para";

// Wenn wir einen Drucker verwenden, der PostScript unterstützt, um unser Dokument zu drucken,
// Dieser Befehl wird den gesamten Bereich, den wir in "field.PostScriptGroup" angegeben haben, weiß machen.
field.PrinterInstructions = "erasepage";

Assert.AreEqual(" PRINT  erasepage \\p para", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.PRINT.docx");
```

### Siehe auch

* class [FieldPrint](../)
* namensraum [Aspose.Words.Fields](../../fieldprint/)
* Montage [Aspose.Words](../../../)


