---
title: IMailMergeCallback.TagsReplaced
second_title: Aspose.Words för .NET API Referens
description: IMailMergeCallback metod. Anropas när mustaschtexttaggar ersätts med MERGEFIELDfält.
type: docs
weight: 10
url: /sv/net/aspose.words.mailmerging/imailmergecallback/tagsreplaced/
---
## IMailMergeCallback.TagsReplaced method

Anropas när "mustasch"-texttaggar ersätts med MERGEFIELD-fält.

```csharp
public void TagsReplaced()
```

### Exempel

Visar hur man definierar anpassad logik för hantering av händelser under sammanslagning.

```csharp
public void Callback()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Infoga två sammanslagningstaggar som refererar till två kolumner i en datakälla.
    builder.Write("{{FirstName}}");
    builder.Write("{{LastName}}");

    // Skapa en datakälla som bara innehåller en av kolumnerna som våra sammanslagningstaggar refererar till.
    DataTable table = new DataTable("Test");
    table.Columns.Add("FirstName");
    table.Rows.Add("John");
    table.Rows.Add("Jane");

    // Konfigurera vår kopplingsfil för att använda alternativa kopplingstaggar.
    doc.MailMerge.UseNonMergeFields = true;

    // Se sedan till att e-postsammanslagningen kommer att konvertera taggar, som vår "LastName"-tagg,
    // till MERGEFIELDs i sammanslagningsdokumenten.
    doc.MailMerge.PreserveUnusedTags = false;

    MailMergeTagReplacementCounter counter = new MailMergeTagReplacementCounter();
    doc.MailMerge.MailMergeCallback = counter;
    doc.MailMerge.Execute(table);

    Assert.AreEqual(1, counter.TagsReplacedCount);
}

/// <summary>
/// Räknar antalet gånger en kopplingskoppling ersätter kopplingsetiketter som den inte kunde fylla med data med MERGEFIELDs.
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

### Se även

* property [UseNonMergeFields](../../mailmerge/usenonmergefields/)
* interface [IMailMergeCallback](../)
* namnutrymme [Aspose.Words.MailMerging](../../imailmergecallback/)
* hopsättning [Aspose.Words](../../../)


