---
title: MailMerge.GetRegionsByName
second_title: Referencia de API de Aspose.Words para .NET
description: MailMerge método. Devuelve una colección de regiones de combinación de correspondencia con el nombre especificado.
type: docs
weight: 240
url: /es/net/aspose.words.mailmerging/mailmerge/getregionsbyname/
---
## MailMerge.GetRegionsByName method

Devuelve una colección de regiones de combinación de correspondencia con el nombre especificado.

```csharp
public IList<MailMergeRegionInfo> GetRegionsByName(string regionName)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| regionName | String | Nombre de la región (sin distinción entre mayúsculas y minúsculas). |

### Valor_devuelto

La lista de regiones.

### Ejemplos

Muestra cómo crear, enumerar y leer regiones de combinación de correspondencia.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// etiquetas "TableStart" y "TableEnd", que van dentro de MERGEFIELD,
// denota las cadenas que significan el comienzo y el final de las regiones de combinación de correspondencia.
Assert.AreEqual("TableStart", doc.MailMerge.RegionStartTag);
Assert.AreEqual("TableEnd", doc.MailMerge.RegionEndTag);

// Utilice estas etiquetas para iniciar y finalizar una región de combinación de correo denominada "MailMergeRegion1",
// que contendrá MERGEFIELDs para dos columnas.
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.InsertField(" MERGEFIELD Column1");
builder.Write(", ");
builder.InsertField(" MERGEFIELD Column2");
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// Podemos realizar un seguimiento de las regiones de fusión y sus columnas observando estas colecciones.
IList<MailMergeRegionInfo> regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(1, regions.Count);
Assert.AreEqual("MailMergeRegion1", regions[0].Name);

string[] mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1");

Assert.AreEqual("Column1", mergeFieldNames[0]);
Assert.AreEqual("Column2", mergeFieldNames[1]);

// Inserta una región con el mismo nombre dentro de la región existente, lo que la convertirá en padre.
// Ahora un campo "Columna2" estará dentro de una nueva región.
builder.MoveToField(regions[0].Fields[1], false); 
builder.InsertField(" MERGEFIELD TableStart:MailMergeRegion1");
builder.MoveToField(regions[0].Fields[1], true);
builder.InsertField(" MERGEFIELD TableEnd:MailMergeRegion1");

// Si buscamos el nombre de regiones duplicadas usando el método "GetRegionsByName",
// devolverá todas esas regiones en una colección.
regions = doc.MailMerge.GetRegionsByName("MailMergeRegion1");

Assert.AreEqual(2, regions.Count);
// Compruebe que la segunda región ahora tiene una región principal.
Assert.AreEqual("MailMergeRegion1", regions[1].ParentRegion.Name);

mergeFieldNames = doc.MailMerge.GetFieldNamesForRegion("MailMergeRegion1", 1);

Assert.AreEqual("Column2", mergeFieldNames[0]);
```

### Ver también

* class [MailMergeRegionInfo](../../mailmergeregioninfo/)
* class [MailMerge](../)
* espacio de nombres [Aspose.Words.MailMerging](../../mailmerge/)
* asamblea [Aspose.Words](../../../)


