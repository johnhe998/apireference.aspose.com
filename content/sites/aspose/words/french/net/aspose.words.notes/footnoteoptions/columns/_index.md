---
title: FootnoteOptions.Columns
second_title: Référence de l'API Aspose.Words pour .NET
description: FootnoteOptions propriété. Spécifie le nombre de colonnes avec lesquelles la zone des notes de bas de page est formatée.
type: docs
weight: 10
url: /fr/net/aspose.words.notes/footnoteoptions/columns/
---
## FootnoteOptions.Columns property

Spécifie le nombre de colonnes avec lesquelles la zone des notes de bas de page est formatée.

```csharp
public int Columns { get; set; }
```

### Remarques

Si cette propriété a la valeur 0, la zone des notes de bas de page est formatée avec un nombre de colonnes basé sur le nombre de colonnes sur la page affichée. La valeur par défaut est 0.

### Exemples

Montre comment diviser la section des notes de bas de page en un nombre donné de colonnes.

```csharp
Document doc = new Document(MyDir + "Footnotes and endnotes.docx");
doc.FootnoteOptions.Columns = 2;
doc.Save(ArtifactsDir + "Document.FootnoteColumns.docx");
```

### Voir également

* class [FootnoteOptions](../)
* espace de noms [Aspose.Words.Notes](../../footnoteoptions/)
* Assemblée [Aspose.Words](../../../)


