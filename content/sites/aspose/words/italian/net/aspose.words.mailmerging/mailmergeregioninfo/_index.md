---
title: Class MailMergeRegionInfo
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.MailMerging.MailMergeRegionInfo classe. Contiene informazioni su una regione di stampa unione.
type: docs
weight: 3640
url: /it/net/aspose.words.mailmerging/mailmergeregioninfo/
---
## MailMergeRegionInfo class

Contiene informazioni su una regione di stampa unione.

```csharp
public class MailMergeRegionInfo
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [EndField](../../aspose.words.mailmerging/mailmergeregioninfo/endfield/) { get; } | Restituisce un campo finale per la regione. |
| [Fields](../../aspose.words.mailmerging/mailmergeregioninfo/fields/) { get; } | Restituisce un elenco di campi figlio. |
| [Level](../../aspose.words.mailmerging/mailmergeregioninfo/level/) { get; } | Restituisce il livello di annidamento per la regione. |
| [Name](../../aspose.words.mailmerging/mailmergeregioninfo/name/) { get; } | Restituisce il nome della regione. |
| [ParentRegion](../../aspose.words.mailmerging/mailmergeregioninfo/parentregion/) { get; } | Restituisce le informazioni sulla regione padre (null per la regione di primo livello). |
| [Regions](../../aspose.words.mailmerging/mailmergeregioninfo/regions/) { get; } | Restituisce un elenco di regioni figlie. |
| [StartField](../../aspose.words.mailmerging/mailmergeregioninfo/startfield/) { get; } | Restituisce un campo iniziale per la regione. |

### Esempi

Mostra come verificare le aree di stampa unione.

```csharp
Document doc = new Document(MyDir + "Mail merge regions.docx");

// Restituisce una gerarchia completa di regioni di unione che contengono MERGEFIELD disponibili nel documento.
MailMergeRegionInfo regionInfo = doc.MailMerge.GetRegionsHierarchy();

// Ottieni le regioni principali nel documento.
IList<MailMergeRegionInfo> topRegions = regionInfo.Regions;

Assert.AreEqual(2, topRegions.Count);
Assert.AreEqual("Region1", topRegions[0].Name);
Assert.AreEqual("Region2", topRegions[1].Name);
Assert.AreEqual(1, topRegions[0].Level);
Assert.AreEqual(1, topRegions[1].Level);

// Ottieni la regione nidificata nella prima regione in alto.
IList<MailMergeRegionInfo> nestedRegions = topRegions[0].Regions;

Assert.AreEqual(2, nestedRegions.Count);
Assert.AreEqual("NestedRegion1", nestedRegions[0].Name);
Assert.AreEqual("NestedRegion2", nestedRegions[1].Name);
Assert.AreEqual(2, nestedRegions[0].Level);
Assert.AreEqual(2, nestedRegions[1].Level);

// Ottieni l'elenco dei campi all'interno della prima regione in alto.
IList<Field> fieldList = topRegions[0].Fields;

Assert.AreEqual(4, fieldList.Count);

FieldMergeField startFieldMergeField = nestedRegions[0].StartField;

Assert.AreEqual("TableStart:NestedRegion1", startFieldMergeField.FieldName);

FieldMergeField endFieldMergeField = nestedRegions[0].EndField;

Assert.AreEqual("TableEnd:NestedRegion1", endFieldMergeField.FieldName);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* assemblea [Aspose.Words](../../)


