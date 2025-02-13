---
title: MailMerge.UseNonMergeFields
second_title: Aspose.Words für .NET-API-Referenz
description: MailMerge eigendom. Wenn true gibt an dass der Seriendruck zusätzlich zu MERGEFIELDFeldern in einigen anderen Feldtypen und auch in fieldNameTags durchgeführt wird.
type: docs
weight: 150
url: /de/net/aspose.words.mailmerging/mailmerge/usenonmergefields/
---
## MailMerge.UseNonMergeFields property

Wenn „true“, gibt an, dass der Seriendruck zusätzlich zu MERGEFIELD-Feldern in einigen anderen Feldtypen und auch in „{{fieldName}}“-Tags durchgeführt wird.

```csharp
public bool UseNonMergeFields { get; set; }
```

### Bemerkungen

Normalerweise wird der Seriendruck nur in MERGEFIELD-Feldern ausgeführt, aber mehrere Kunden haben ihre reporting mit anderen Feldern erstellt und viele Dokumente auf diese Weise erstellt. Um die Migration zu vereinfachen (und weil dieser -Ansatz von mehreren Kunden unabhängig voneinander verwendet wurde) wurde die Möglichkeit des Seriendrucks in andere Felder eingeführt.

Wann **Verwenden Sie NonMergeFields** auf true gesetzt ist, führt Aspose.Words einen Seriendruck in den folgenden Feldern durch:

MERGEFIELD-Feldname

MACROBUTTON NOMACRO FieldName

WENN 0 = 0 "{Feldname}" ""

Auch wann **UserNonMergeFields** auf true gesetzt ist, führt Aspose.Words einen Seriendruck in Text tags "{{fieldName}}" durch. Dies sind keine Felder, sondern nur Text-Tags.

### Beispiele

Zeigt, wie das Erscheinungsbild alternativer Seriendruck-Tags beibehalten wird, die während eines Seriendrucks nicht verwendet werden.

```csharp
public void PreserveUnusedTags(bool preserveUnusedTags)
{
    Document doc = CreateSourceDocWithAlternativeMergeFields();
    DataTable dataTable = CreateSourceTablePreserveUnusedTags();

    // Standardmäßig platziert ein Seriendruck Daten aus jeder Zeile einer Tabelle in MERGEFIELDs, die Spalten in dieser Tabelle benennen. 
    // Unser Dokument hat keine solchen Felder, aber es hat Klartext-Tags, die von geschweiften Klammern eingeschlossen sind.
    // Wenn wir das Flag "PreserveUnusedTags" auf "true" setzen, könnten wir diese Tags als MERGEFIELDs behandeln
    // damit unser Seriendruck Daten aus der Datenquelle an diesen Tags einfügen kann.
    // Wenn wir das Flag "PreserveUnusedTags" auf "false" setzen,
    // Der Seriendruck konvertiert diese Tags in MERGEFIELDs und lässt sie ungefüllt.
    doc.MailMerge.PreserveUnusedTags = preserveUnusedTags;
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.PreserveUnusedTags.docx");

    // Unser Dokument hat ein Tag für eine Spalte namens "Spalte2", die in der Tabelle nicht vorhanden ist.
    // Wenn wir das Flag "PreserveUnusedTags" auf "false" setzen, then the mail merge will convert this tag into a MERGEFIELD.
    Assert.AreEqual(doc.GetText().Contains("{{ Column2 }}"), preserveUnusedTags);

    if (preserveUnusedTags)
        Assert.AreEqual(0, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
    else
        Assert.AreEqual(1, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
}

/// <summary>
/// Erstellen Sie ein Dokument und fügen Sie zwei Klartext-Tags hinzu, die während eines Seriendrucks als MERGEFIELDs fungieren können.
/// </summary>
private static Document CreateSourceDocWithAlternativeMergeFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("{{ Column1 }}");
    builder.Writeln("{{ Column2 }}");

    // Unsere Tags werden nur dann als Ziele für Seriendruckdaten registriert, wenn wir dies auf „true“ setzen.
    doc.MailMerge.UseNonMergeFields = true;

    return doc;
}

/// <summary>
/// Erstellen Sie eine einfache Datentabelle mit einer Spalte.
/// </summary>
private static DataTable CreateSourceTablePreserveUnusedTags()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Rows.Add(new object[] { "Value1" });

    return dataTable;
}
```

### Siehe auch

* class [MailMerge](../)
* namensraum [Aspose.Words.MailMerging](../../mailmerge/)
* Montage [Aspose.Words](../../../)


