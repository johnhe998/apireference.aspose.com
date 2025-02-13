---
title: MailMerge.ExecuteWithRegionsADO
second_title: Aspose.Words für .NET-API-Referenz
description: MailMerge methode. Führt den Seriendruck von einem ADORecordsetObjekt in das Dokument mit Seriendruckbereichen durch.
type: docs
weight: 210
url: /de/net/aspose.words.mailmerging/mailmerge/executewithregionsado/
---
## MailMerge.ExecuteWithRegionsADO method

Führt den Seriendruck von einem ADO-Recordset-Objekt in das Dokument mit Seriendruckbereichen durch.

```csharp
public void ExecuteWithRegionsADO(object recordset, string tableName)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| recordset | Object | ADO Recordset- oder Record-Objekt. |
| tableName | String | Name des Seriendruckbereichs im zu füllenden Dokument. |

### Bemerkungen

Diese Methode ist nützlich, wenn Sie beabsichtigen, Aspose.Words-Klassen als COM-Objekte aus nicht verwaltetem Code zu verwenden, z. B. eine Anwendung, die mit ASP oder Visual Basic 6.0 erstellt wurde.

Weitere Informationen finden Sie in der Beschreibung von MailMerge.ExecuteWithRegions(DataTable).

### Beispiele

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

Zeigt, wie Sie einen Seriendruck mit mehreren Regionen ausführen, der mit Daten aus einem ADO-Dataset kompiliert wurde.

```csharp
public void ExecuteWithRegionsADO()
{
    Document doc = CreateSourceDocADOMailMergeWithRegions();

    // Um mit ADO DataSets zu arbeiten, müssen wir einen Verweis auf die Microsoft ActiveX Data Objects-Bibliothek hinzufügen,
    // die in der .NET-Distribution enthalten und in "adodb.dll" gespeichert ist.
    ADODB.Connection connection = new ADODB.Connection();

    // Erstellen Sie eine Verbindungszeichenfolge, die auf die Datenbankdatei "Northwind" zeigt
    // in unserem lokalen Dateisystem und öffnen Sie eine Verbindung.
    string connectionString = @"Provider=Microsoft.Jet.OLEDB.4.0;Data Source=" + DatabaseDir + "Northwind.mdb";
    connection.Open(connectionString);

    // Füllen Sie unser DataSet, indem Sie einen SQL-Befehl in unserer Datenbank ausführen.
    // Die Namen der Spalten in der Ergebnistabelle müssen übereinstimmen
    // zu den Werten der MERGEFIELDS, die unsere Daten aufnehmen.
    string command = "SELECT FirstName, LastName, City FROM Employees";

    ADODB.Recordset recordset = new ADODB.Recordset();
    recordset.Open(command, connection);

    // Führen Sie einen Seriendruck nur für die erste Region aus und füllen Sie deren MERGEFIELDS mit Daten aus dem Datensatz.
    doc.MailMerge.ExecuteWithRegionsADO(recordset, "MergeRegion1");

    // Den Datensatz schließen und mit Daten aus einer anderen SQL-Abfrage erneut öffnen.
    command = "SELECT * FROM Customers";

    recordset.Close();
    recordset.Open(command, connection);

    // Führen Sie einen zweiten Seriendruck für die zweite Region aus und speichern Sie das Dokument.
    doc.MailMerge.ExecuteWithRegionsADO(recordset, "MergeRegion2");

    doc.Save(ArtifactsDir + "MailMerge.ExecuteWithRegionsADO.docx");
}

/// <summary>
/// Erstellen Sie ein Dokument mit zwei Seriendruckbereichen.
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

### Siehe auch

* class [MailMerge](../)
* namensraum [Aspose.Words.MailMerging](../../mailmerge/)
* Montage [Aspose.Words](../../../)


