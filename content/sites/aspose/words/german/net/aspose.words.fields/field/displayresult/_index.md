---
title: Field.DisplayResult
second_title: Aspose.Words für .NET-API-Referenz
description: Field eigendom. Ruft den Text ab der das angezeigte Feldergebnis darstellt.
type: docs
weight: 10
url: /de/net/aspose.words.fields/field/displayresult/
---
## Field.DisplayResult property

Ruft den Text ab, der das angezeigte Feldergebnis darstellt.

```csharp
public string DisplayResult { get; }
```

### Bemerkungen

Die[`UpdateListLabels`](../../../aspose.words/document/updatelistlabels/) Methode muss aufgerufen werden, um den korrekten Wert für the zu erhalten[`FieldListNum`](../../fieldlistnum/) ,[`FieldAutoNum`](../../fieldautonum/) ,[`FieldAutoNumOut`](../../fieldautonumout/) und[`FieldAutoNumLgl`](../../fieldautonumlgl/) Felder.

### Beispiele

Zeigt, wie Sie den echten Text abrufen, den ein Feld im Dokument anzeigt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("This document was written by ");
FieldAuthor fieldAuthor = (FieldAuthor)builder.InsertField(FieldType.FieldAuthor, true);
fieldAuthor.AuthorName = "John Doe";

// Wir können die DisplayResult-Eigenschaft verwenden, um den genauen Text zu überprüfen
// Ein Feld würde an seiner Stelle im Dokument angezeigt.
Assert.AreEqual(string.Empty, fieldAuthor.DisplayResult);

 // Felder behalten keine genauen Ergebniswerte in Echtzeit bei.
// Um sicherzustellen, dass unsere Felder jederzeit genaue Ergebnisse anzeigen,
// wie direkt vor einer Speicheroperation müssen wir sie manuell aktualisieren.
fieldAuthor.Update();

Assert.AreEqual("John Doe", fieldAuthor.DisplayResult);

doc.Save(ArtifactsDir + "Field.DisplayResult.docx");
```

### Siehe auch

* class [Field](../)
* namensraum [Aspose.Words.Fields](../../field/)
* Montage [Aspose.Words](../../../)


