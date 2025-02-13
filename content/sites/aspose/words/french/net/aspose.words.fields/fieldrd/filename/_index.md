---
title: FieldRD.FileName
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldRD propriété. Obtient ou définit le nom du fichier à inclure lors de la génération dune table des matières dune table des références ou dun index.
type: docs
weight: 20
url: /fr/net/aspose.words.fields/fieldrd/filename/
---
## FieldRD.FileName property

Obtient ou définit le nom du fichier à inclure lors de la génération d'une table des matières, d'une table des références ou d'un index.

```csharp
public string FileName { get; set; }
```

### Exemples

Indique d'utiliser le champ RD pour créer une table des matières à partir des en-têtes d'autres documents.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Utiliser un constructeur de document pour insérer une table des matières,
// puis ajoutez une entrée pour la table des matières sur la page suivante.
builder.InsertField(FieldType.FieldTOC, true);
builder.InsertBreak(BreakType.PageBreak);
builder.CurrentParagraph.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("TOC entry from within this document");

// Insère un champ RD, qui fait référence à un autre document du système de fichiers local dans sa propriété FileName.
// La table des matières acceptera désormais également tous les titres du document référencé comme entrées pour sa table.
FieldRD field = (FieldRD)builder.InsertField(FieldType.FieldRefDoc, true);
field.FileName = "ReferencedDocument.docx";
field.IsPathRelative = true;

Assert.AreEqual(" RD  ReferencedDocument.docx \\f", field.GetFieldCode());

 // Crée le document auquel le champ RD fait référence et insère un titre.
// Cet en-tête apparaîtra comme une entrée dans le champ TOC de notre premier document.
Document referencedDoc = new Document();
DocumentBuilder refDocBuilder = new DocumentBuilder(referencedDoc);
refDocBuilder.CurrentParagraph.ParagraphFormat.StyleName = "Heading 1";
refDocBuilder.Writeln("TOC entry from referenced document");
referencedDoc.Save(ArtifactsDir + "ReferencedDocument.docx");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.RD.docx");
```

### Voir également

* class [FieldRD](../)
* espace de noms [Aspose.Words.Fields](../../fieldrd/)
* Assemblée [Aspose.Words](../../../)


