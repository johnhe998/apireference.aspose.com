---
title: FieldOptions.FileName
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldOptions propriété. Obtient ou définit le nom de fichier du document.
type: docs
weight: 120
url: /fr/net/aspose.words.fields/fieldoptions/filename/
---
## FieldOptions.FileName property

Obtient ou définit le nom de fichier du document.

```csharp
public string FileName { get; set; }
```

### Remarques

Cette propriété est utilisée par le[`FieldFileName`](../../fieldfilename/) champ avec une priorité plus élevée que le[`OriginalFileName`](../../../aspose.words/document/originalfilename/) propriété.

### Exemples

Montre comment utiliser FieldOptions pour remplacer la valeur par défaut du champ FILENAME.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
builder.Writeln();

// Ce champ FILENAME affichera le nom de fichier du système local du document que nous avons chargé.
FieldFileName field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.Update();

Assert.AreEqual(" FILENAME ", field.GetFieldCode());
Assert.AreEqual("Document.docx", field.Result);

builder.Writeln();

// Par défaut, le champ FILENAME affiche le nom du fichier, mais pas son chemin d'accès complet au système de fichiers local.
// Nous pouvons définir un indicateur pour lui faire afficher le chemin complet du fichier.
field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.IncludeFullPath = true;
field.Update();

Assert.AreEqual(MyDir + "Document.docx", field.Result);

// Nous pouvons également définir une valeur pour cette propriété à
// remplace la valeur affichée par le champ FILENAME.
doc.FieldOptions.FileName = "FieldOptions.FILENAME.docx";
field.Update();

Assert.AreEqual(" FILENAME  \\p", field.GetFieldCode());
Assert.AreEqual("FieldOptions.FILENAME.docx", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + doc.FieldOptions.FileName);
```

### Voir également

* class [FieldOptions](../)
* espace de noms [Aspose.Words.Fields](../../fieldoptions/)
* Assemblée [Aspose.Words](../../../)


