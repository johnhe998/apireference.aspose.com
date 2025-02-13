---
title: MailMerge.CleanupParagraphsWithPunctuationMarks
second_title: Référence de l'API Aspose.Words pour .NET
description: MailMerge propriété. Obtient ou définit une valeur indiquant si les paragraphes avec des signes de ponctuation sont considérés comme vides et doivent être supprimés si leRemoveEmptyParagraphs loption est spécifiée.
type: docs
weight: 20
url: /fr/net/aspose.words.mailmerging/mailmerge/cleanupparagraphswithpunctuationmarks/
---
## MailMerge.CleanupParagraphsWithPunctuationMarks property

Obtient ou définit une valeur indiquant si les paragraphes avec des signes de ponctuation sont considérés comme vides et doivent être supprimés si leRemoveEmptyParagraphs l'option est spécifiée.

```csharp
public bool CleanupParagraphsWithPunctuationMarks { get; set; }
```

### Remarques

La valeur par défaut est`vrai` .

Voici la liste complète des signes de ponctuation nettoyables :

* !
* ,
* .
* :
* ;
* ?
* ¡
* ¿

### Exemples

Montre comment supprimer des paragraphes avec des signes de ponctuation après une opération de fusion et publipostage.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.InsertField("MERGEFIELD", "Option_1");
mergeFieldOption1.FieldName = "Option_1";

builder.Write(punctuationMark);

FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.InsertField("MERGEFIELD", "Option_2");
mergeFieldOption2.FieldName = "Option_2";

// Configurez la propriété "CleanupOptions" pour supprimer tous les paragraphes vides que ce publipostage créerait.
doc.MailMerge.CleanupOptions = MailMergeCleanupOptions.RemoveEmptyParagraphs;

// Définir la propriété "CleanupParagraphsWithPunctuationMarks" sur "true" comptera également les paragraphes
// avec des signes de ponctuation vides et obtiendra l'opération de fusion et publipostage pour les supprimer également.
// Définition de la propriété "CleanupParagraphsWithPunctuationMarks" sur "false"
// supprimera les paragraphes vides, mais pas ceux avec des signes de ponctuation.
// Voici une liste des signes de ponctuation concernés par cette propriété : "!", ",", ".", ":", ";", "?", "¡", "¿".
doc.MailMerge.CleanupParagraphsWithPunctuationMarks = cleanupParagraphsWithPunctuationMarks;

doc.MailMerge.Execute(new[] { "Option_1", "Option_2" }, new object[] { null, null });

doc.Save(ArtifactsDir + "MailMerge.RemoveColonBetweenEmptyMergeFields.docx");
```

### Voir également

* class [MailMerge](../)
* espace de noms [Aspose.Words.MailMerging](../../mailmerge/)
* Assemblée [Aspose.Words](../../../)


