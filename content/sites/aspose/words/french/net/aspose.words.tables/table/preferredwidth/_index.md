---
title: Table.PreferredWidth
second_title: Référence de l'API Aspose.Words pour .NET
description: Table propriété. Obtient ou définit la largeur préférée du tableau.
type: docs
weight: 220
url: /fr/net/aspose.words.tables/table/preferredwidth/
---
## Table.PreferredWidth property

Obtient ou définit la largeur préférée du tableau.

```csharp
public PreferredWidth PreferredWidth { get; set; }
```

### Remarques

La valeur par défaut est[`Auto`](../../preferredwidth/auto/).

### Exemples

Montre comment définir un tableau pour qu'il s'adapte automatiquement à 50 % de la largeur de la page.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell #1");
builder.InsertCell();
builder.Write("Cell #2");
builder.InsertCell();
builder.Write("Cell #3");

table.PreferredWidth = PreferredWidth.FromPercent(50);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableWithPreferredWidth.docx");
```

### Voir également

* class [PreferredWidth](../../preferredwidth/)
* class [Table](../)
* espace de noms [Aspose.Words.Tables](../../table/)
* Assemblée [Aspose.Words](../../../)


