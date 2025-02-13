---
title: MailMerge.MergeWholeDocument
second_title: Aspose.Words für .NET-API-Referenz
description: MailMerge eigendom. Ruft einen Wert ab oder legt einen Wert fest der angibt ob Felder im gesamten Dokument aktualisiert werden während ein Seriendruck mit Regionen ausgeführt wird.
type: docs
weight: 70
url: /de/net/aspose.words.mailmerging/mailmerge/mergewholedocument/
---
## MailMerge.MergeWholeDocument property

Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob Felder im gesamten Dokument aktualisiert werden, während ein Seriendruck mit Regionen ausgeführt wird.

```csharp
public bool MergeWholeDocument { get; set; }
```

### Bemerkungen

Der Standardwert ist **FALSCH** .

### Beispiele

Zeigt die Beziehung zwischen Serienbriefen mit Regionen und Feldaktualisierungen.

```csharp
public void MergeWholeDocument(bool mergeWholeDocument)
{
    Document doc = CreateSourceDocMergeWholeDocument();
    DataTable dataTable = CreateSourceTableMergeWholeDocument();

    // Wenn wir das Flag "MergeWholeDocument" auf "true" setzen,
    // Der Seriendruck mit Regionen aktualisiert jedes Feld im Dokument.
    // Wenn wir das Flag "MergeWholeDocument" auf "false" setzen, werden beim Seriendruck nur Felder aktualisiert
    // innerhalb des Seriendruckbereichs, dessen Name mit dem Namen der Datenquellentabelle übereinstimmt.
    doc.MailMerge.MergeWholeDocument = mergeWholeDocument;
    doc.MailMerge.ExecuteWithRegions(dataTable);

    // Der Seriendruck aktualisiert nur das QUOTE-Feld außerhalb der Seriendruckregion
    // wenn wir das "MergeWholeDocument"-Flag auf "true" setzen.
    doc.Save(ArtifactsDir + "MailMerge.MergeWholeDocument.docx");

    Assert.True(doc.GetText().Contains("This QUOTE field is inside the \"MyTable\" merge region."));
    Assert.AreEqual(mergeWholeDocument, 
        doc.GetText().Contains("This QUOTE field is outside of the \"MyTable\" merge region."));
}

/// <summary>
/// Erstellen Sie ein Dokument mit einem Seriendruckbereich, der zu einer Datenquelle namens "MyTable" gehört.
/// Fügen Sie ein QUOTE-Feld innerhalb dieses Bereichs und ein weiteres außerhalb davon ein.
/// </summary>
private static Document CreateSourceDocMergeWholeDocument()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    FieldQuote field = (FieldQuote)builder.InsertField(FieldType.FieldQuote, true);
    field.Text = "This QUOTE field is outside of the \"MyTable\" merge region.";

    builder.InsertParagraph();
    builder.InsertField(" MERGEFIELD TableStart:MyTable");

    field = (FieldQuote)builder.InsertField(FieldType.FieldQuote, true);
    field.Text = "This QUOTE field is inside the \"MyTable\" merge region.";
    builder.InsertParagraph();

    builder.InsertField(" MERGEFIELD MyColumn");
    builder.InsertField(" MERGEFIELD TableEnd:MyTable");

    return doc;
}

/// <summary>
/// Erstellen Sie eine Datentabelle, die in einem Seriendruck verwendet wird.
/// </summary>
private static DataTable CreateSourceTableMergeWholeDocument()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("MyColumn");
    dataTable.Rows.Add(new object[] { "MyValue" });

    return dataTable;
}
```

### Siehe auch

* class [MailMerge](../)
* namensraum [Aspose.Words.MailMerging](../../mailmerge/)
* Montage [Aspose.Words](../../../)


