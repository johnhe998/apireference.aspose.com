---
title: FieldDatabase.LastRecord
second_title: Aspose.Words für .NET-API-Referenz
description: FieldDatabase eigendom. Holt oder setzt die ganzzahlige Satznummer des letzten einzufügenden Datensatzes.
type: docs
weight: 80
url: /de/net/aspose.words.fields/fielddatabase/lastrecord/
---
## FieldDatabase.LastRecord property

Holt oder setzt die ganzzahlige Satznummer des letzten einzufügenden Datensatzes.

```csharp
public string LastRecord { get; set; }
```

### Beispiele

Zeigt, wie Daten aus einer Datenbank extrahiert und als Feld in ein Dokument eingefügt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Dieses DATABASE-Feld führt eine Abfrage in einer Datenbank aus und zeigt das Ergebnis in einer Tabelle an.
FieldDatabase field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query = "SELECT * FROM [Products]";

Assert.AreEqual($" DATABASE  \\d \"{DatabaseDir.Replace("\\", "\\\\") + "Northwind.mdb"}\" \\c \"DSN=MS Access Databases\" \\s \"SELECT * FROM [Products]\"", 
    field.GetFieldCode());

// Fügen Sie ein weiteres DATABASE-Feld mit einer komplexeren Abfrage ein, die alle Produkte in absteigender Reihenfolge nach Bruttoumsatz sortiert.
field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query =
    "SELECT [Products].ProductName, FORMAT(SUM([Order Details].UnitPrice * (1 - [Order Details].Discount) * [Order Details].Quantity), 'Currency') AS GrossSales " +
    "FROM([Products] " +
    "LEFT JOIN[Order Details] ON[Products].[ProductID] = [Order Details].[ProductID]) " +
    "GROUP BY[Products].ProductName " +
    "ORDER BY SUM([Order Details].UnitPrice* (1 - [Order Details].Discount) * [Order Details].Quantity) DESC";

// Diese Eigenschaften haben dieselbe Funktion wie LIMIT- und TOP-Klauseln.
// Konfigurieren Sie sie so, dass nur die Zeilen 1 bis 10 des Abfrageergebnisses in der Tabelle des Felds angezeigt werden.
field.FirstRecord = "1";
field.LastRecord = "10";

// Diese Eigenschaft ist der Index des Formats, das wir für unsere Tabelle verwenden möchten. Die Liste der Tabellenformate befindet sich im Menü "Tabellen-AutoFormat...".
// das erscheint, wenn wir ein DATENBANK-Feld in Microsoft Word erstellen. Index #10 entspricht dem Format „Bunte 3“.
field.TableFormat = "10";

// Die Eigenschaft FormatAttribute ist eine Zeichenfolgendarstellung einer Ganzzahl, die mehrere Flags speichert.
// Wir können das Format, auf das die TableFormat-Eigenschaft zeigt, partiell anwenden, indem wir verschiedene Flags in dieser Eigenschaft setzen.
// Die von uns verwendete Zahl ist die Summe einer Kombination von Werten, die verschiedenen Aspekten des Tabellenstils entsprechen.
// 63 steht für 1 (Rahmen) + 2 (Schattierung) + 4 (Schriftart) + 8 (Farbe) + 16 (Autofit) + 32 (Überschriftenzeilen).
field.FormatAttributes = "63";
field.InsertHeadings = true;
field.InsertOnceOnMailMerge = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATABASE.docx");
```

### Siehe auch

* class [FieldDatabase](../)
* namensraum [Aspose.Words.Fields](../../fielddatabase/)
* Montage [Aspose.Words](../../../)


