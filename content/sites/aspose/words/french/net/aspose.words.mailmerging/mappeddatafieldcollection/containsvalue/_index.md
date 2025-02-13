---
title: MappedDataFieldCollection.ContainsValue
second_title: Référence de l'API Aspose.Words pour .NET
description: MappedDataFieldCollection méthode. Détermine si un mappage du champ spécifié dans la source de données existe dans la collection.
type: docs
weight: 60
url: /fr/net/aspose.words.mailmerging/mappeddatafieldcollection/containsvalue/
---
## MappedDataFieldCollection.ContainsValue method

Détermine si un mappage du champ spécifié dans la source de données existe dans la collection.

```csharp
public bool ContainsValue(string dataSourceFieldName)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| dataSourceFieldName | String | Nom sensible à la casse du champ dans la source de données. |

### Return_Value

True si l'élément est trouvé dans la collection ; sinon, faux.

### Exemples

Montre comment mapper des colonnes de données et des MERGEFIELD avec des noms différents afin que les données soient transférées entre eux lors d'un publipostage.

```csharp
public void MappedDataFieldCollection()
{
    Document doc = CreateSourceDocMappedDataFields();
    DataTable dataTable = CreateSourceTableMappedDataFields();

    // La table a une colonne nommée "Column2", mais il n'y a pas de MERGEFIELD avec ce nom.
    // De plus, nous avons un MERGEFIELD nommé "Column3", mais la source de données n'a pas de colonne portant ce nom.
    // Si les données de "Column2" conviennent au MERGEFIELD "Column3",
    // nous pouvons mapper ce nom de colonne au MERGEFIELD dans la paire clé/valeur "MappedDataFields".
    MappedDataFieldCollection mappedDataFields = doc.MailMerge.MappedDataFields;

    // Nous pouvons lier un nom de colonne de source de données à un nom MERGEFIELD comme celui-ci.
    mappedDataFields.Add("MergeFieldName", "DataSourceColumnName");

    // Liez la colonne de la source de données nommée "Column2" aux MERGEFIELDs nommés "Column3".
    mappedDataFields.Add("Column3", "Column2");

    // Le nom MERGEFIELD est la "clé" du nom de colonne de source de données respectif "valeur".
    Assert.AreEqual("DataSourceColumnName", mappedDataFields["MergeFieldName"]);
    Assert.True(mappedDataFields.ContainsKey("MergeFieldName"));
    Assert.True(mappedDataFields.ContainsValue("DataSourceColumnName"));

    // Maintenant, si nous exécutons ce publipostage, les MERGEFIELD "Column3" prendront les données de "Column2" de la table.
    doc.MailMerge.Execute(dataTable);

    doc.Save(ArtifactsDir + "MailMerge.MappedDataFieldCollection.docx");

    // Nous pouvons parcourir les éléments de cette collection.
    Assert.AreEqual(2, mappedDataFields.Count);

    using (IEnumerator<KeyValuePair<string, string>> enumerator = mappedDataFields.GetEnumerator())
        while (enumerator.MoveNext())
            Console.WriteLine(
                $"Column named {enumerator.Current.Value} is mapped to MERGEFIELDs named {enumerator.Current.Key}");

    // Nous pouvons également supprimer des éléments de la collection.
    mappedDataFields.Remove("MergeFieldName");

    Assert.False(mappedDataFields.ContainsKey("MergeFieldName"));
    Assert.False(mappedDataFields.ContainsValue("DataSourceColumnName"));

    mappedDataFields.Clear();

    Assert.AreEqual(0, mappedDataFields.Count);
}

/// <summary>
/// Créer un document avec 2 MERGEFIELDs, dont l'un n'a pas de
/// colonne correspondante dans la table de données de la méthode ci-dessous.
/// </summary>
private static Document CreateSourceDocMappedDataFields()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(" MERGEFIELD Column1");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD Column3");

    return doc;
}

/// <summary>
/// Créer un tableau de données avec 2 colonnes, dont une n'a pas de
/// MERGEFIELD correspondant dans le document source de la méthode ci-dessus.
/// </summary>
private static DataTable CreateSourceTableMappedDataFields()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("Column1");
    dataTable.Columns.Add("Column2");
    dataTable.Rows.Add(new object[] { "Value1", "Value2" });

    return dataTable;
}
```

### Voir également

* class [MappedDataFieldCollection](../)
* espace de noms [Aspose.Words.MailMerging](../../mappeddatafieldcollection/)
* Assemblée [Aspose.Words](../../../)


