---
title: MailMerge.ExecuteWithRegionsADO
second_title: Référence de l'API Aspose.Words pour .NET
description: MailMerge méthode. Effectue une fusion et publipostage à partir dun objet ADO Recordset dans le document avec des régions de fusion et publipostage.
type: docs
weight: 210
url: /fr/net/aspose.words.mailmerging/mailmerge/executewithregionsado/
---
## MailMerge.ExecuteWithRegionsADO method

Effectue une fusion et publipostage à partir d'un objet ADO Recordset dans le document avec des régions de fusion et publipostage.

```csharp
public void ExecuteWithRegionsADO(object recordset, string tableName)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| recordset | Object | Jeu d'enregistrements ADO ou objet Record. |
| tableName | String | Nom de la région de fusion et publipostage dans le document à remplir. |

### Remarques

Cette méthode est utile lorsque vous avez l'intention d'utiliser les classes Aspose.Words en tant qu'objets COM à partir de code non managé, comme une application créée à l'aide de ASP ou de Visual Basic 6.0.

Pour plus d'informations, consultez la description de MailMerge.ExecuteWithRegions(DataTable).

### Exemples

```csharp
[VBScript]

Dim RS
Set RS = CreateObject("ADODB.Recordset")
RS.Open _
    "SELECT * FROM AsposeWordOrderDetails WHERE OrderId = 10444 ORDER BY ProductID", _
    "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=Northwind.mdb"

Dim Helper
Set Helper = CreateObject("Aspose.Words.ComHelper")

Dim Doc
Set Doc = Helper.Open("Invoice.doc")

Doc.MailMerge.ExecuteWithRegionsADO RS, "OrderDetails"
Doc.Save "Invoice Out VBScript.doc"
```

Montre comment exécuter une fusion et publipostage avec plusieurs régions, compilées avec les données d'un jeu de données ADO.

```csharp
public void ExecuteWithRegionsADO()
{
    Document doc = CreateSourceDocADOMailMergeWithRegions();

    // Pour travailler avec les DataSets ADO, nous devrons ajouter une référence à la bibliothèque Microsoft ActiveX Data Objects,
    // qui est inclus dans la distribution .NET et stocké dans "adodb.dll".
    ADODB.Connection connection = new ADODB.Connection();

    // Crée une chaîne de connexion qui pointe vers le fichier de base de données "Northwind"
    // dans notre système de fichiers local et ouvrez une connexion.
    string connectionString = @"Provider=Microsoft.Jet.OLEDB.4.0;Data Source=" + DatabaseDir + "Northwind.mdb";
    connection.Open(connectionString);

    // Remplir notre DataSet en exécutant une commande SQL sur notre base de données.
    // Les noms des colonnes de la table résultat devront correspondre
    // aux valeurs des MERGEFIELDS qui accueilleront nos données.
    string command = "SELECT FirstName, LastName, City FROM Employees";

    ADODB.Recordset recordset = new ADODB.Recordset();
    recordset.Open(command, connection);

    // Exécute un publipostage uniquement sur la première région, en remplissant ses MERGEFIELDS avec les données du jeu d'enregistrements.
    doc.MailMerge.ExecuteWithRegionsADO(recordset, "MergeRegion1");

    // Ferme le jeu d'enregistrements et le rouvre avec les données d'une autre requête SQL.
    command = "SELECT * FROM Customers";

    recordset.Close();
    recordset.Open(command, connection);

    // Exécutez un deuxième publipostage sur la deuxième région et enregistrez le document.
    doc.MailMerge.ExecuteWithRegionsADO(recordset, "MergeRegion2");

    doc.Save(ArtifactsDir + "MailMerge.ExecuteWithRegionsADO.docx");
}

/// <summary>
/// Créer un document avec deux régions de fusion et publipostage.
/// </summary>
private static Document CreateSourceDocADOMailMergeWithRegions()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("\tEmployees: ");
    builder.InsertField(" MERGEFIELD TableStart:MergeRegion1");
    builder.InsertField(" MERGEFIELD FirstName");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD LastName");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD City");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion1");
    builder.InsertParagraph();

    builder.Writeln("\tCustomers: ");
    builder.InsertField(" MERGEFIELD TableStart:MergeRegion2");
    builder.InsertField(" MERGEFIELD ContactName");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD Address");
    builder.Write(", ");
    builder.InsertField(" MERGEFIELD City");
    builder.InsertField(" MERGEFIELD TableEnd:MergeRegion2");

    return doc;
}
```

### Voir également

* class [MailMerge](../)
* espace de noms [Aspose.Words.MailMerging](../../mailmerge/)
* Assemblée [Aspose.Words](../../../)


