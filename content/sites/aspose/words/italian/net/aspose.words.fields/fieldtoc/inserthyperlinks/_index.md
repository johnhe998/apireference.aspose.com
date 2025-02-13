---
title: FieldToc.InsertHyperlinks
second_title: Aspose.Words per .NET API Reference
description: FieldToc proprietà. Ottiene o imposta se creare collegamenti ipertestuali alle voci del sommario.
type: docs
weight: 100
url: /it/net/aspose.words.fields/fieldtoc/inserthyperlinks/
---
## FieldToc.InsertHyperlinks property

Ottiene o imposta se creare collegamenti ipertestuali alle voci del sommario.

```csharp
public bool InsertHyperlinks { get; set; }
```

### Esempi

Mostra come inserire un sommario e popolarlo con voci basate sugli stili di intestazione.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("MyBookmark");

    // Inserisce un campo TOC, che compilerà tutte le intestazioni in un sommario.
    // Per ogni intestazione, questo campo creerà una riga con il testo in quello stile di intestazione a sinistra,
    // e la pagina in cui compare l'intestazione a destra.
    FieldToc field = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

    // Usa la proprietà BookmarkName per elencare solo le intestazioni
    // che appaiono entro i limiti di un segnalibro con il nome "MyBookmark".
    field.BookmarkName = "MyBookmark";

    // Il testo con uno stile di intestazione integrato, ad esempio "Intestazione 1", applicato ad esso verrà conteggiato come intestazione.
    // Possiamo nominare stili aggiuntivi da raccogliere come intestazioni dal TOC in questa proprietà e nei relativi livelli TOC.
    field.CustomStyles = "Quote; 6; Intense Quote; 7";

    // Per impostazione predefinita, i livelli Styles/TOC sono separati da una virgola nella proprietà CustomStyles,
    // ma possiamo impostare un delimitatore personalizzato in questa proprietà.
    doc.FieldOptions.CustomTocStyleSeparator = ";";

    // Configura il campo per escludere tutte le intestazioni con livelli di sommario al di fuori di questo intervallo.
    field.HeadingLevelRange = "1-3";

    // Il sommario non visualizzerà i numeri di pagina delle intestazioni i cui livelli di sommario rientrano in questo intervallo.
    field.PageNumberOmittingLevelRange = "2-5";

     // Imposta una stringa personalizzata che separerà ogni intestazione dal numero di pagina.
    field.EntrySeparator = "-";
    field.InsertHyperlinks = true;
    field.HideInWebLayout = false;
    field.PreserveLineBreaks = true;
    field.PreserveTabs = true;
    field.UseParagraphOutlineLevel = false;

    InsertNewPageWithHeading(builder, "First entry", "Heading 1");
    builder.Writeln("Paragraph text.");
    InsertNewPageWithHeading(builder, "Second entry", "Heading 1");
    InsertNewPageWithHeading(builder, "Third entry", "Quote");
    InsertNewPageWithHeading(builder, "Fourth entry", "Intense Quote");

    // Queste due intestazioni avranno i numeri di pagina omessi perché rientrano nell'intervallo "2-5".
    InsertNewPageWithHeading(builder, "Fifth entry", "Heading 2");
    InsertNewPageWithHeading(builder, "Sixth entry", "Heading 3");

    // Questa voce non viene visualizzata perché "Intestazione 4" è al di fuori dell'intervallo "1-3" che abbiamo impostato in precedenza.
    InsertNewPageWithHeading(builder, "Seventh entry", "Heading 4");

    builder.EndBookmark("MyBookmark");
    builder.Writeln("Paragraph text.");

    // Questa voce non viene visualizzata perché è al di fuori del segnalibro specificato dal sommario.
    InsertNewPageWithHeading(builder, "Eighth entry", "Heading 1");

    Assert.AreEqual(" TOC  \\b MyBookmark \\t \"Quote; 6; Intense Quote; 7\" \\o 1-3 \\n 2-5 \\p - \\h \\x \\w", field.GetFieldCode());

    field.UpdatePageNumbers();
    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.TOC.docx");

/// <summary>
/// Inizia una nuova pagina e inserisci un paragrafo di uno stile specificato.
/// </summary>
public void InsertNewPageWithHeading(DocumentBuilder builder, string captionText, string styleName)
{
    builder.InsertBreak(BreakType.PageBreak);
    string originalStyle = builder.ParagraphFormat.StyleName;
    builder.ParagraphFormat.Style = builder.Document.Styles[styleName];
    builder.Writeln(captionText);
    builder.ParagraphFormat.Style = builder.Document.Styles[originalStyle];
}
```

### Guarda anche

* class [FieldToc](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldtoc/)
* assemblea [Aspose.Words](../../../)


