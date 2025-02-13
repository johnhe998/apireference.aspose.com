---
title: FieldSkipIf.ComparisonOperator
second_title: Aspose.Words für .NET-API-Referenz
description: FieldSkipIf eigendom. Ruft den Vergleichsoperator ab oder setzt ihn.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldskipif/comparisonoperator/
---
## FieldSkipIf.ComparisonOperator property

Ruft den Vergleichsoperator ab oder setzt ihn.

```csharp
public string ComparisonOperator { get; set; }
```

### Beispiele

Zeigt, wie Seiten in einem Seriendruck mit dem SKIPIF-Feld übersprungen werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ein SKIPIF-Feld einfügen. Wenn die aktuelle Zeile eines Serienbriefvorgangs die Bedingung erfüllt
// was die Ausdrücke dieses Feldes angeben, dann bricht der Serienbriefvorgang die aktuelle Zeile ab,
// verwirft das aktuelle Seriendruckdokument und geht dann sofort zur nächsten Zeile, um mit dem nächsten Seriendruckdokument zu beginnen.
FieldSkipIf fieldSkipIf = (FieldSkipIf) builder.InsertField(FieldType.FieldSkipIf, true);

// Verschieben Sie den Builder zum Trennzeichen des SKIPIF-Felds, damit wir ein MERGEFIELD innerhalb des SKIPIF-Felds platzieren können.
builder.MoveTo(fieldSkipIf.Separator);
FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Department";

// Das MERGEFIELD bezieht sich auf die Spalte "Abteilung" in unserer Datentabelle. Wenn eine Zeile aus dieser Tabelle
// in der Spalte „Abteilung“ den Wert „HR“ hat, erfüllt diese Zeile die Bedingung.
fieldSkipIf.LeftExpression = "=";
fieldSkipIf.RightExpression = "HR";

// Fügen Sie Inhalt zu unserem Dokument hinzu, erstellen Sie die Datenquelle und führen Sie den Seriendruck aus.
builder.MoveToDocumentEnd();
builder.Write("Dear ");
fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Name";
builder.Writeln(", ");

 // Diese Tabelle hat drei Zeilen, und eine davon erfüllt die Bedingung unseres SKIPIF-Felds.
// Der Seriendruck erzeugt zwei Seiten.
DataTable table = new DataTable("Employees");
table.Columns.Add("Name");
table.Columns.Add("Department");
table.Rows.Add("John Doe", "Sales");
table.Rows.Add("Jane Doe", "Accounting");
table.Rows.Add("John Cardholder", "HR");

doc.MailMerge.Execute(table);
doc.Save(ArtifactsDir + "Field.SKIPIF.docx");
```

Zeigt, wie die Felder MERGEREC und MERGESEQ verwendet werden, um Seriendruckdatensätze in den Ausgabedokumenten eines Seriendrucks zu nummerieren und zu zählen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Name";
builder.Writeln(",");

// Ein MERGEREC-Feld gibt die Zeilennummer der zusammenzuführenden Daten in jedem Zusammenführungsausgabedokument aus.
builder.Write("\nRow number of record in data source: ");
FieldMergeRec fieldMergeRec = (FieldMergeRec)builder.InsertField(FieldType.FieldMergeRec, true);

Assert.AreEqual(" MERGEREC ", fieldMergeRec.GetFieldCode());

// Ein MERGESEQ-Feld zählt die Anzahl erfolgreicher Zusammenführungen und gibt den aktuellen Wert auf jeder entsprechenden Seite aus.
// Wenn ein Seriendruck keine Zeilen überspringt und keine SKIP/SKIPIF/NEXT/NEXTIF-Felder aufruft, sind alle Zusammenführungen erfolgreich.
// Die Felder MERGESEQ und MERGEREC zeigen die gleichen Ergebnisse ihres erfolgreichen Seriendrucks an.
builder.Write("\nSuccessful merge number: ");
FieldMergeSeq fieldMergeSeq = (FieldMergeSeq)builder.InsertField(FieldType.FieldMergeSeq, true);

Assert.AreEqual(" MERGESEQ ", fieldMergeSeq.GetFieldCode());

// Füge ein SKIPIF-Feld ein, das eine Zusammenführung überspringt, wenn der Name "John Doe" ist.
FieldSkipIf fieldSkipIf = (FieldSkipIf)builder.InsertField(FieldType.FieldSkipIf, true);
builder.MoveTo(fieldSkipIf.Separator);
fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Name";
fieldSkipIf.LeftExpression = "=";
fieldSkipIf.RightExpression = "John Doe";

// Erstellen Sie eine Datenquelle mit 3 Zeilen, von denen eine "John Doe" als Wert für die Spalte "Name" enthält.
// Da ein SKIPIF-Feld einmal durch diesen Wert ausgelöst wird, hat die Ausgabe unseres Seriendrucks 2 statt 3 Seiten.
// Auf Seite 1 zeigen die Felder MERGESEQ und MERGEREC beide "1" an.
// Auf Seite 2 zeigt das MERGEREC-Feld "3" und das MERGESEQ-Feld "2" an.
DataTable table = new DataTable("Employees");
table.Columns.Add("Name");
table.Rows.Add(new[] { "Jane Doe" });
table.Rows.Add(new[] { "John Doe" });
table.Rows.Add(new[] { "Joe Bloggs" });

doc.MailMerge.Execute(table);
doc.Save(ArtifactsDir + "Field.MERGEREC.MERGESEQ.docx");
```

### Siehe auch

* class [FieldSkipIf](../)
* namensraum [Aspose.Words.Fields](../../fieldskipif/)
* Montage [Aspose.Words](../../../)


