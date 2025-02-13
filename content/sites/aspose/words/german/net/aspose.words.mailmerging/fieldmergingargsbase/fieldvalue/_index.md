---
title: FieldMergingArgsBase.FieldValue
second_title: Aspose.Words für .NET-API-Referenz
description: FieldMergingArgsBase eigendom. Ruft den Wert des Felds aus der Datenquelle ab oder legt ihn fest.
type: docs
weight: 50
url: /de/net/aspose.words.mailmerging/fieldmergingargsbase/fieldvalue/
---
## FieldMergingArgsBase.FieldValue property

Ruft den Wert des Felds aus der Datenquelle ab oder legt ihn fest.

```csharp
public object FieldValue { get; set; }
```

### Bemerkungen

Diese Eigenschaft enthält einen Wert, der gerade aus Ihrer Datenquelle für dieses Feld von der Seriendruck-Engine ausgewählt wurde. Sie können den Wert auch ersetzen, indem Sie die Eigenschaft festlegen.

### Beispiele

Zeigt, wie Werte bearbeitet werden, die MERGEFIELDs erhalten, wenn ein Seriendruck stattfindet.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Fügen Sie einige MERGEFIELDs mit Formatschaltern ein, die die Werte bearbeiten, die sie während eines Seriendrucks erhalten.
    builder.InsertField("MERGEFIELD text_Field1 \\* Caps", null);
    builder.Write(", ");
    builder.InsertField("MERGEFIELD text_Field2 \\* Upper", null);
    builder.Write(", ");
    builder.InsertField("MERGEFIELD numeric_Field1 \\# 0.0", null);

    builder.Document.MailMerge.FieldMergingCallback = new FieldValueMergingCallback();

    builder.Document.MailMerge.Execute(
        new string[] { "text_Field1", "text_Field2", "numeric_Field1" },
        new object[] { "Field 1", "Field 2", 10 });
    string t = doc.GetText().Trim();
    Assert.AreEqual("Merge Value For \"Text_Field1\": Field 1, MERGE VALUE FOR \"TEXT_FIELD2\": FIELD 2, 10000.0", doc.GetText().Trim());
}

/// <summary>
/// Bearbeitet die Werte, die MERGEFIELDs während eines Seriendrucks erhalten.
/// Der Name eines MERGEFIELD muss ein Präfix haben, damit dieser Callback auf seinen Wert wirkt.
/// </summary>
private class FieldValueMergingCallback : IFieldMergingCallback
{
    /// <summary>
    /// Wird aufgerufen, wenn bei einem Seriendruck Daten in einem MERGEFIELD zusammengeführt werden.
    /// </summary>
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs e)
    {
        if (e.FieldName.StartsWith("text_"))
            e.FieldValue = $"Merge value for \"{e.FieldName}\": {(string)e.FieldValue}";
        else if (e.FieldName.StartsWith("numeric_"))
            e.FieldValue = (int)e.FieldValue * 1000;
    }

    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs e)
    {
        // Nichts tun.
    }
}
```

### Siehe auch

* class [FieldMergingArgsBase](../)
* namensraum [Aspose.Words.MailMerging](../../fieldmergingargsbase/)
* Montage [Aspose.Words](../../../)


