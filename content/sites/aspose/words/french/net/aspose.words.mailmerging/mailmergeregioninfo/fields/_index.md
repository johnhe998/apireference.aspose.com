---
title: MailMergeRegionInfo.Fields
second_title: Référence de l'API Aspose.Words pour .NET
description: MailMergeRegionInfo propriété. Renvoie une liste de champs enfants.
type: docs
weight: 20
url: /fr/net/aspose.words.mailmerging/mailmergeregioninfo/fields/
---
## MailMergeRegionInfo.Fields property

Renvoie une liste de champs enfants.

```csharp
public IList<Field> Fields { get; }
```

### Exemples

Montre comment vérifier les régions de fusion et publipostage.

```csharp
Document doc = new Document(MyDir + "Mail merge regions.docx");

// Renvoie une hiérarchie complète des régions de fusion contenant les MERGEFIELD disponibles dans le document.
MailMergeRegionInfo regionInfo = doc.MailMerge.GetRegionsHierarchy();

// Récupère les régions supérieures dans le document.
IList<MailMergeRegionInfo> topRegions = regionInfo.Regions;

Assert.AreEqual(2, topRegions.Count);
Assert.AreEqual("Region1", topRegions[0].Name);
Assert.AreEqual("Region2", topRegions[1].Name);
Assert.AreEqual(1, topRegions[0].Level);
Assert.AreEqual(1, topRegions[1].Level);

// Récupère la région imbriquée dans la première région supérieure.
IList<MailMergeRegionInfo> nestedRegions = topRegions[0].Regions;

Assert.AreEqual(2, nestedRegions.Count);
Assert.AreEqual("NestedRegion1", nestedRegions[0].Name);
Assert.AreEqual("NestedRegion2", nestedRegions[1].Name);
Assert.AreEqual(2, nestedRegions[0].Level);
Assert.AreEqual(2, nestedRegions[1].Level);

// Récupère la liste des champs à l'intérieur de la première région supérieure.
IList<Field> fieldList = topRegions[0].Fields;

Assert.AreEqual(4, fieldList.Count);

FieldMergeField startFieldMergeField = nestedRegions[0].StartField;

Assert.AreEqual("TableStart:NestedRegion1", startFieldMergeField.FieldName);

FieldMergeField endFieldMergeField = nestedRegions[0].EndField;

Assert.AreEqual("TableEnd:NestedRegion1", endFieldMergeField.FieldName);
```

### Voir également

* class [Field](../../../aspose.words.fields/field/)
* class [MailMergeRegionInfo](../)
* espace de noms [Aspose.Words.MailMerging](../../mailmergeregioninfo/)
* Assemblée [Aspose.Words](../../../)


