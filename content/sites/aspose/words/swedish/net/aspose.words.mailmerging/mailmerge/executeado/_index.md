---
title: MailMerge.ExecuteADO
second_title: Aspose.Words för .NET API Referens
description: MailMerge metod. Utför epostkoppling från ett ADO Recordsetobjekt till dokumentet.
type: docs
weight: 190
url: /sv/net/aspose.words.mailmerging/mailmerge/executeado/
---
## MailMerge.ExecuteADO method

Utför e-postkoppling från ett ADO Recordset-objekt till dokumentet.

```csharp
public void ExecuteADO(object recordset)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| recordset | Object | ADO Recordset eller Record-objekt. |

### Anmärkningar

Den här metoden är användbar när du tänker använda Aspose.Words-klasserna as COM-objekt från ohanterad kod, till exempel ett program byggt med ASP eller Visual Basic 6.0.

Denna metod ignorerarRemoveUnusedRegions alternativ.

För mer information se beskrivning av MailMerge.Execute(DataTable).

### Exempel

```csharp
[VBScript]

Dim RS
Set RS = CreateObject("ADODB.Recordset")
RS.Open _
    "SELECT TOP 50 * FROM Customers ORDER BY Country, CompanyName", _
    "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=Northwind.mdb"

Dim License
Set License = CreateObject("Aspose.Words.License")
License.SetLicense "C:\MyPath\MyLicense.lic"

Dim Helper
Set Helper = CreateObject("Aspose.Words.ComHelper")
Dim Doc
Set Doc = Helper.Open("CustomerLabels.doc")

Doc.MailMerge.ExecuteADO RS
Doc.Save "C:\MyPath\CustomerLabels Out VBScript.doc"
```

Visar hur man kör en sammankoppling med data från en ADO-datauppsättning.

```csharp
public void ExecuteADO()
{
    Document doc = CreateSourceDocADOMailMerge();

    // För att arbeta med ADO DataSets måste vi lägga till en referens till Microsoft ActiveX Data Objects-biblioteket,
    // som ingår i .NET-distributionen och lagras i "adodb.dll".
    ADODB.Connection connection = new ADODB.Connection();

    // Skapa en anslutningssträng som pekar på databasfilen "Northwind".
    // i vårt lokala filsystem och öppna en anslutning.
    string connectionString = @"Provider=Microsoft.Jet.OLEDB.4.0;Data Source=" + DatabaseDir + "Northwind.mdb";
    connection.Open(connectionString);

    // Fyll i vår datauppsättning genom att köra ett SQL-kommando på vår databas.
    // Namnen på kolumnerna i resultattabellen måste överensstämma
    // till värdena för MERGEFIELDS som kommer att rymma våra data.
    const string command = @"SELECT ProductName, QuantityPerUnit, UnitPrice FROM Products";

    ADODB.Recordset recordset = new ADODB.Recordset();
    recordset.Open(command, connection);

    // Kör sammankopplingen och spara dokumentet.
    doc.MailMerge.ExecuteADO(recordset);
    doc.Save(ArtifactsDir + "MailMerge.ExecuteADO.docx");
}

/// <summary>
/// Skapa ett tomt dokument och fyll i det med MERGEFIELDS som kommer att acceptera data när en e-postsammanslagning körs.
/// </summary>
private static Document CreateSourceDocADOMailMerge()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Write("Product:\t");
    builder.InsertField(" MERGEFIELD ProductName");
    builder.Writeln();
    builder.InsertField(" MERGEFIELD QuantityPerUnit");
    builder.Write(" for $");
    builder.InsertField(" MERGEFIELD UnitPrice");

    return doc;
}
```

### Se även

* class [MailMerge](../)
* namnutrymme [Aspose.Words.MailMerging](../../mailmerge/)
* hopsättning [Aspose.Words](../../../)


