---
title: IMailMergeCallback.TagsReplaced
second_title: Aspose.Words für .NET-API-Referenz
description: IMailMergeCallback methode. Wird aufgerufen wenn SchnurrbartTextTags durch MERGEFIELDFelder ersetzt werden.
type: docs
weight: 10
url: /de/net/aspose.words.mailmerging/imailmergecallback/tagsreplaced/
---
## IMailMergeCallback.TagsReplaced method

Wird aufgerufen, wenn „Schnurrbart“-Text-Tags durch MERGEFIELD-Felder ersetzt werden.

```csharp
public void TagsReplaced()
```

### Beispiele

Zeigt, wie benutzerdefinierte Logik für die Behandlung von Ereignissen während des Seriendrucks definiert wird.

```csharp
public void Callback()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Zwei Seriendruck-Tags einfügen, die auf zwei Spalten in einer Datenquelle verweisen.
    builder.Write("{{FirstName}}");
    builder.Write("{{LastName}}");

    // Erstellen Sie eine Datenquelle, die nur eine der Spalten enthält, auf die unsere Merge-Tags verweisen.
    DataTable table = new DataTable("Test");
    table.Columns.Add("FirstName");
    table.Rows.Add("John");
    table.Rows.Add("Jane");

    // Konfigurieren Sie unseren Seriendruck, um alternative Serienbrief-Tags zu verwenden.
    doc.MailMerge.UseNonMergeFields = true;

    // Stellen Sie dann sicher, dass der Seriendruck Tags konvertiert, wie z. B. unser "LastName"-Tag,
    // in MERGEFIELDs in den Zusammenführungsdokumenten.
    doc.MailMerge.PreserveUnusedTags = false;

    MailMergeTagReplacementCounter counter = new MailMergeTagReplacementCounter();
    doc.MailMerge.MailMergeCallback = counter;
    doc.MailMerge.Execute(table);

    Assert.AreEqual(1, counter.TagsReplacedCount);
}

/// <summary>
/// Zählt, wie oft ein Seriendruck Serienbrief-Tags ersetzt, die nicht mit MERGEFIELDs mit Daten gefüllt werden konnten.
/// </summary>
private class MailMergeTagReplacementCounter : IMailMergeCallback
{
    public void TagsReplaced()
    {
        TagsReplacedCount++;
    }

    public int TagsReplacedCount { get; private set; }
}
```

### Siehe auch

* property [UseNonMergeFields](../../mailmerge/usenonmergefields/)
* interface [IMailMergeCallback](../)
* namensraum [Aspose.Words.MailMerging](../../imailmergecallback/)
* Montage [Aspose.Words](../../../)


