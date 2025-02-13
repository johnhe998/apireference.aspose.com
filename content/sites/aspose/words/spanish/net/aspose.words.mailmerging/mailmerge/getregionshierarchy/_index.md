---
title: MailMerge.GetRegionsHierarchy
second_title: Referencia de API de Aspose.Words para .NET
description: MailMerge método. Devuelve una jerarquía completa de regiones con campos disponibles en el documento.
type: docs
weight: 250
url: /es/net/aspose.words.mailmerging/mailmerge/getregionshierarchy/
---
## MailMerge.GetRegionsHierarchy method

Devuelve una jerarquía completa de regiones (con campos) disponibles en el documento.

```csharp
public MailMergeRegionInfo GetRegionsHierarchy()
```

### Valor_devuelto

Jerarquía de regiones.

### Observaciones

La jerarquía se devuelve en forma de[`MailMergeRegionInfo`](../../mailmergeregioninfo/) clase.

### Ejemplos

Muestra cómo verificar las regiones de combinación de correspondencia.

```csharp
Document doc = new Document(MyDir + "Mail merge regions.docx");

// Devuelve una jerarquía completa de regiones de fusión que contienen MERGEFIELD disponibles en el documento.
MailMergeRegionInfo regionInfo = doc.MailMerge.GetRegionsHierarchy();

// Obtenga las regiones principales en el documento.
IList<MailMergeRegionInfo> topRegions = regionInfo.Regions;

Assert.AreEqual(2, topRegions.Count);
Assert.AreEqual("Region1", topRegions[0].Name);
Assert.AreEqual("Region2", topRegions[1].Name);
Assert.AreEqual(1, topRegions[0].Level);
Assert.AreEqual(1, topRegions[1].Level);

// Obtenga la región anidada en la primera región superior.
IList<MailMergeRegionInfo> nestedRegions = topRegions[0].Regions;

Assert.AreEqual(2, nestedRegions.Count);
Assert.AreEqual("NestedRegion1", nestedRegions[0].Name);
Assert.AreEqual("NestedRegion2", nestedRegions[1].Name);
Assert.AreEqual(2, nestedRegions[0].Level);
Assert.AreEqual(2, nestedRegions[1].Level);

// Obtener una lista de campos dentro de la primera región superior.
IList<Field> fieldList = topRegions[0].Fields;

Assert.AreEqual(4, fieldList.Count);

FieldMergeField startFieldMergeField = nestedRegions[0].StartField;

Assert.AreEqual("TableStart:NestedRegion1", startFieldMergeField.FieldName);

FieldMergeField endFieldMergeField = nestedRegions[0].EndField;

Assert.AreEqual("TableEnd:NestedRegion1", endFieldMergeField.FieldName);
```

### Ver también

* class [MailMergeRegionInfo](../../mailmergeregioninfo/)
* class [MailMerge](../)
* espacio de nombres [Aspose.Words.MailMerging](../../mailmerge/)
* asamblea [Aspose.Words](../../../)


