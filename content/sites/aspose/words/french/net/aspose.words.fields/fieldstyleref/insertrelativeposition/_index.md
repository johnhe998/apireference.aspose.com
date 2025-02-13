---
title: FieldStyleRef.InsertRelativePosition
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldStyleRef propriété. Obtient ou définit sil faut insérer la position relative du paragraphe référencé.
type: docs
weight: 50
url: /fr/net/aspose.words.fields/fieldstyleref/insertrelativeposition/
---
## FieldStyleRef.InsertRelativePosition property

Obtient ou définit s'il faut insérer la position relative du paragraphe référencé.

```csharp
public bool InsertRelativePosition { get; set; }
```

### Exemples

Montre comment utiliser les champs STYLEREF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crée une liste basée sur un modèle de liste Microsoft Word.
Aspose.Words.Lists.List list = doc.Lists.Add(Aspose.Words.Lists.ListTemplate.NumberDefault);

// Cette liste générée affichera "1.a )".
 // L'espace avant le crochet est un caractère non délimiteur, que nous pouvons supprimer.
list.ListLevels[0].NumberFormat = "\x0000.";
list.ListLevels[1].NumberFormat = "\x0001 )";

// Ajoute du texte et applique des styles de paragraphe auxquels les champs STYLEREF feront référence.
builder.ListFormat.List = list;
builder.ListFormat.ListIndent();
builder.ParagraphFormat.Style = doc.Styles["List Paragraph"];
builder.Writeln("Item 1");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln("Item 2");
builder.ParagraphFormat.Style = doc.Styles["List Paragraph"];
builder.Writeln("Item 3");
builder.ListFormat.RemoveNumbers();
builder.ParagraphFormat.Style = doc.Styles["Normal"];

// Place un champ STYLEREF dans l'en-tête et affiche le premier texte de style "List Paragraph" dans le document.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
FieldStyleRef field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "List Paragraph";

// Place un champ STYLEREF dans le pied de page et affiche le dernier texte.
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "List Paragraph";
field.SearchFromBottom = true;

builder.MoveToDocumentEnd();

// Nous pouvons également utiliser les champs STYLEREF pour référencer les numéros de liste des listes.
builder.Write("\nParagraph number: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumber = true;

builder.Write("\nParagraph number, relative context: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInRelativeContext = true;

builder.Write("\nParagraph number, full context: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInFullContext = true;

builder.Write("\nParagraph number, full context, non-delimiter chars suppressed: ");
field = (FieldStyleRef)builder.InsertField(FieldType.FieldStyleRef, true);
field.StyleName = "Quote";
field.InsertParagraphNumberInFullContext = true;
field.SuppressNonDelimiters = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.STYLEREF.docx");
```

### Voir également

* class [FieldStyleRef](../)
* espace de noms [Aspose.Words.Fields](../../fieldstyleref/)
* Assemblée [Aspose.Words](../../../)


