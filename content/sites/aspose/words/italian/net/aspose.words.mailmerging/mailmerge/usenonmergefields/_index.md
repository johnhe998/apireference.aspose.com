---
title: MailMerge.UseNonMergeFields
second_title: Aspose.Words per .NET API Reference
description: MailMerge proprietà. Se true specifica che oltre ai campi MERGEFIELD la stampa unione viene eseguita in alcuni altri tipi di campi e anche nei tag fieldName.
type: docs
weight: 150
url: /it/net/aspose.words.mailmerging/mailmerge/usenonmergefields/
---
## MailMerge.UseNonMergeFields property

Se true, specifica che oltre ai campi MERGEFIELD, la stampa unione viene eseguita in alcuni altri tipi di campi e anche nei tag "{{fieldName}}".

```csharp
public bool UseNonMergeFields { get; set; }
```

### Osservazioni

Normalmente, la stampa unione viene eseguita solo nei campi MERGEFIELD, ma diversi clienti hanno compilato il proprio reporting utilizzando altri campi e molti documenti sono stati creati in questo modo. Per semplificare la migrazione (e poiché questo approccio è stato utilizzato in modo indipendente da diversi clienti) è stata introdotta la possibilità di eseguire la stampa unione in altri campi.

quando **UseNonMergeFields** è impostato su true, Aspose.Words eseguirà la stampa unione nei seguenti campi:

MERGEFIELD Nome campo

MACROBUTTON NOMACRO NomeCampo

SE 0 = 0 "{NomeCampo}" ""

Inoltre, quando **UserNonMergeFields** è impostato su true, Aspose.Words eseguirà la stampa unione in tag di testo "{{fieldName}}". Questi non sono campi, ma solo tag di testo.

### Esempi

Mostra come preservare l'aspetto dei tag di stampa unione alternativi che non vengono utilizzati durante una stampa unione.

```csharp
public void PreserveUnusedTags(bool preserveUnusedTags)
{
    Document doc = CreateSourceDocWithAlternativeMergeFields();
    DataTable dataTable = CreateSourceTablePreserveUnusedTags();

    // Per impostazione predefinita, una stampa unione inserisce i dati da ogni riga di una tabella in MERGEFIELD, che denominano le colonne in quella tabella. 
    // Il nostro documento non ha tali campi, ma ha tag di testo in chiaro racchiusi tra parentesi graffe.
    // Se impostiamo il flag "PreserveUnusedTags" su "true", potremmo trattare questi tag come MERGEFIELD
    // per consentire alla nostra stampa unione di inserire dati dall'origine dati in quei tag.
    // Se impostiamo il flag "PreserveUnusedTags" su "false",
    // la stampa unione convertirà questi tag in MERGEFIELD e li lascerà vuoti.
    doc.MailMerge.PreserveUnusedTags = preserveUnusedTags;
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.PreserveUnusedTags.docx");

    // Il nostro documento ha un tag per una colonna denominata "Colonna2", che non esiste nella tabella.
    // Se impostiamo il flag "PreserveUnusedTags" su "false", then the mail merge will convert this tag into a MERGEFIELD.
    Assert.AreEqual(doc.GetText().Contains("{{ Column2 }}"), preserveUnusedTags);

    if (preserveUnusedTags)
        Assert.AreEqual(0, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
    else
        Assert.AreEqual(1, doc.Range.Fields.Count(f => f.Type == FieldType.FieldMergeField));
}

/// <summary>
/// Crea un documento e aggiungi due tag di testo normale che possono fungere da MERGEFIELD durante una stampa unione.
/// </summary>
private static Document CreateSourceDocWithAlternativeMergeFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("{{ Column1 }}");
    builder.Writeln("{{ Column2 }}");

    // I nostri tag verranno registrati come destinazioni per i dati di stampa unione solo se lo impostiamo su true.
    doc.MailMerge.UseNonMergeFields = true;

    return doc;
}

/// <summary>
/// Crea una semplice tabella di dati con una colonna.
/// </summary>
private static DataTable CreateSourceTablePreserveUnusedTags()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Rows.Add(new object[] { "Value1" });

    return dataTable;
}
```

### Guarda anche

* class [MailMerge](../)
* spazio dei nomi [Aspose.Words.MailMerging](../../mailmerge/)
* assemblea [Aspose.Words](../../../)


