---
title: MailMerge.RegionEndTag
second_title: Référence de l'API Aspose.Words pour .NET
description: MailMerge propriété. Obtient ou définit une balise de fin de région de fusion et publipostage.
type: docs
weight: 90
url: /fr/net/aspose.words.mailmerging/mailmerge/regionendtag/
---
## MailMerge.RegionEndTag property

Obtient ou définit une balise de fin de région de fusion et publipostage.

```csharp
public string RegionEndTag { get; set; }
```

### Exemples

Montre comment créer, répertorier et lire des régions de fusion et publipostage.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Les balises "TableStart" et "TableEnd", qui vont à l'intérieur des MERGEFIELD,
// dénotent les chaînes qui signifient le début et la fin des régions de fusion et publipostage.
Assert.AreEqual("TableStart", doc.MailMerge.RegionStartTag);
Assert.AreEqual("TableEnd", doc.MailMerge.RegionEndTag);

// Utilisez ces balises pour démarrer et terminer une région de publipostage nommée "MailMergeRegion1",
// qui contiendra les MERGEFIELD pour deux colonnes.
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.InsertField(" MERGEFIELD Column1");
builder.Write(", ");
builder.InsertField(" MERGEFIELD Column2");
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// Nous pouvons suivre les régions de fusion et leurs colonnes en examinant ces collections.
IList<MailMergeRegionInfo> regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(1, regions.Count);
Assert.AreEqual("MailMergeRegion1", regions[0].Name);

string[] mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1");

Assert.AreEqual("Column1", mergeFieldNames[0]);
Assert.AreEqual("Column2", mergeFieldNames[1]);

// Insère une région avec le même nom à l'intérieur de la région existante, ce qui en fera un parent.
// Maintenant, un champ "Column2" sera à l'intérieur d'une nouvelle région.
builder.MoveToField(regions[0].Fields[1], false); 
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.MoveToField(regions[0].Fields[1], true);
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// Si nous recherchons le nom des régions en double à l'aide de la méthode "GetRegionsByName",
// il renverra toutes ces régions dans une collection.
regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(2, regions.Count);
// Vérifiez que la deuxième région a maintenant une région parent.
Assert.AreEqual("MailMergeRegion1", regions[1].ParentRegion.Name);

mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1", 1);

Assert.AreEqual("Column2", mergeFieldNames[0]);
```

### Voir également

* class [MailMerge](../)
* espace de noms [Aspose.Words.MailMerging](../../mailmerge/)
* Assemblée [Aspose.Words](../../../)


