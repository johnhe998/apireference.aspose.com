---
title: CompareOptions.IgnoreCaseChanges
second_title: Référence de l'API Aspose.Words pour .NET
description: CompareOptions propriété. True indique que la comparaison de documents est insensible à la casse. Par défaut la comparaison est sensible à la casse.
type: docs
weight: 30
url: /fr/net/aspose.words.comparing/compareoptions/ignorecasechanges/
---
## CompareOptions.IgnoreCaseChanges property

True indique que la comparaison de documents est insensible à la casse. Par défaut, la comparaison est sensible à la casse.

```csharp
public bool IgnoreCaseChanges { get; set; }
```

### Exemples

Montre comment filtrer des types spécifiques d'éléments de document lors d'une comparaison.

```csharp
// Crée le document d'origine et le remplit avec différents types d'éléments.
Document docOriginal = new Document();
DocumentBuilder builder = new DocumentBuilder(docOriginal);

// Texte de paragraphe référencé avec une note de fin :
builder.Writeln("Hello world! This is the first paragraph.");
builder.InsertFootnote(FootnoteType.Endnote, "Original endnote text.");

// Table:
builder.StartTable();
builder.InsertCell();
builder.Write("Original cell 1 text");
builder.InsertCell();
builder.Write("Original cell 2 text");
builder.EndTable();

// Zone de texte:
Shape textBox = builder.InsertShape(ShapeType.TextBox, 150, 20);
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Original textbox contents");

// Champ DATE :
builder.MoveTo(docOriginal.FirstSection.Body.AppendParagraph(""));
builder.InsertField(" DATE ");

// Commentaire:
Comment newComment = new Comment(docOriginal, "John Doe", "J.D.", DateTime.Now);
newComment.SetText("Original comment.");
builder.CurrentParagraph.AppendChild(newComment);

// Entête:
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("Original header contents.");

// Crée un clone de notre document et effectue une modification rapide sur chacun des éléments du document cloné.
Document docEdited = (Document)docOriginal.Clone(true);
Paragraph firstParagraph = docEdited.FirstSection.Body.FirstParagraph;

firstParagraph.Runs[0].Text = "hello world! this is the first paragraph, after editing.";
firstParagraph.ParagraphFormat.Style = docEdited.Styles[StyleIdentifier.Heading1];
((Footnote)docEdited.GetChild(NodeType.Footnote, 0, true)).FirstParagraph.Runs[1].Text = "Edited endnote text.";
((Table)docEdited.GetChild(NodeType.Table, 0, true)).FirstRow.Cells[1].FirstParagraph.Runs[0].Text = "Edited Cell 2 contents";
((Shape)docEdited.GetChild(NodeType.Shape, 0, true)).FirstParagraph.Runs[0].Text = "Edited textbox contents";
((FieldDate)docEdited.Range.Fields[0]).UseLunarCalendar = true; 
((Comment)docEdited.GetChild(NodeType.Comment, 0, true)).FirstParagraph.Runs[0].Text = "Edited comment.";
docEdited.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].FirstParagraph.Runs[0].Text =
    "Edited header contents.";

// La comparaison de documents crée une révision pour chaque modification dans le document modifié.
// Un objet CompareOptions a une série de drapeaux qui peuvent supprimer les révisions
// sur chaque type d'élément respectif, ignorant effectivement leur changement.
Aspose.Words.Comparing.CompareOptions compareOptions = new Aspose.Words.Comparing.CompareOptions();
compareOptions.IgnoreFormatting = false;
compareOptions.IgnoreCaseChanges = false;
compareOptions.IgnoreComments = false;
compareOptions.IgnoreTables = false;
compareOptions.IgnoreFields = false;
compareOptions.IgnoreFootnotes = false;
compareOptions.IgnoreTextboxes = false;
compareOptions.IgnoreHeadersAndFooters = false;
compareOptions.Target = ComparisonTargetType.New;

docOriginal.Compare(docEdited, "John Doe", DateTime.Now, compareOptions);
docOriginal.Save(ArtifactsDir + "Document.CompareOptions.docx");
```

### Voir également

* class [CompareOptions](../)
* espace de noms [Aspose.Words.Comparing](../../compareoptions/)
* Assemblée [Aspose.Words](../../../)


