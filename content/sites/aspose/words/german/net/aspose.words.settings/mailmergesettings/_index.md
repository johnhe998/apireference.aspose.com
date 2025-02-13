---
title: Class MailMergeSettings
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Settings.MailMergeSettings klas. Gibt alle Seriendruckinformationen für ein Dokument an.
type: docs
weight: 5550
url: /de/net/aspose.words.settings/mailmergesettings/
---
## MailMergeSettings class

Gibt alle Seriendruckinformationen für ein Dokument an.

```csharp
public class MailMergeSettings
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [MailMergeSettings](mailmergesettings/)() | Default_Constructor |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [ActiveRecord](../../aspose.words.settings/mailmergesettings/activerecord/) { get; set; } | Gibt den einsbasierten Index des Datensatzes aus der Datenquelle an, der in Microsoft Word angezeigt werden soll. Der Standardwert ist 1. |
| [AddressFieldName](../../aspose.words.settings/mailmergesettings/addressfieldname/) { get; set; } | Gibt die Spalte innerhalb der Datenquelle an, die E-Mail-Adressen enthält. Der Standardwert ist eine leere Zeichenfolge. |
| [CheckErrors](../../aspose.words.settings/mailmergesettings/checkerrors/) { get; set; } | Gibt die Art der Fehlerberichterstattung an, die von Microsoft Word beim Ausführen eines Seriendrucks durchgeführt werden soll. Der Standardwert istDefault . |
| [ConnectString](../../aspose.words.settings/mailmergesettings/connectstring/) { get; set; } | Gibt die Verbindungszeichenfolge an, die zum Herstellen einer Verbindung mit einer externen Datenquelle verwendet wird. Der Standardwert ist eine leere Zeichenfolge. |
| [DataSource](../../aspose.words.settings/mailmergesettings/datasource/) { get; set; } | Gibt den Pfad zur Seriendruck-Datenquelle an. Der Standardwert ist eine leere Zeichenfolge. |
| [DataType](../../aspose.words.settings/mailmergesettings/datatype/) { get; set; } | Gibt den Typ der Seriendruck-Datenquelle und die Datenzugriffsmethode an. Der Standardwert istDefault . |
| [Destination](../../aspose.words.settings/mailmergesettings/destination/) { get; set; } | Gibt an, wie Microsoft Word die Ergebnisse eines Seriendrucks ausgibt. Der Standardwert istDefault . |
| [DoNotSupressBlankLines](../../aspose.words.settings/mailmergesettings/donotsupressblanklines/) { get; set; } | Gibt an, wie eine Anwendung, die den Seriendruck ausführt, mit Leerzeilen in den zusammengeführten Dokumenten umgehen soll, die aus dem Seriendruck resultieren. Der Standardwert ist`FALSCH` . |
| [HeaderSource](../../aspose.words.settings/mailmergesettings/headersource/) { get; set; } | Gibt den Pfad zur Quelle des Seriendruck-Headers an. Der Standardwert ist eine leere Zeichenfolge. |
| [LinkToQuery](../../aspose.words.settings/mailmergesettings/linktoquery/) { get; set; } | Ich bin mir diesbezüglich nicht sicher. Die Microsoft Word-Automatisierungsreferenz schlägt vor, dass dies angibt, dass die Abfrage jedes Mal ausgeführt wird, wenn das Dokument in Microsoft Word geöffnet wird. Aber die OOXML-Spezifikation schlägt vor, dass dies angibt, dass die Abfrage einen Verweis auf eine externe Abfragedatei enthält, die die eigentliche Abfrage enthält. Der Standardwert ist`FALSCH` . |
| [MailAsAttachment](../../aspose.words.settings/mailmergesettings/mailasattachment/) { get; set; } | Gibt an, dass die während eines Seriendruckvorgangs erstellten Dokumente per E-Mail als Anhang und nicht als als Text der eigentlichen E-Mail gesendet werden sollen. Der Standardwert ist`FALSCH` . |
| [MailSubject](../../aspose.words.settings/mailmergesettings/mailsubject/) { get; set; } | Gibt den Text an, der in der Betreffzeile der E-Mails oder Faxe erscheinen soll, die beim Seriendruck entstehen. Der Standardwert ist ein leerer String. |
| [MainDocumentType](../../aspose.words.settings/mailmergesettings/maindocumenttype/) { get; set; } | Gibt den Hauptdokumenttyp des Seriendrucks an. Der Standardwert istDefault . |
| [Odso](../../aspose.words.settings/mailmergesettings/odso/) { get; set; } | Ruft das Objekt ab oder legt es fest, das die Office Data Source Object (ODSO)-Einstellungen angibt. |
| [Query](../../aspose.words.settings/mailmergesettings/query/) { get; set; } | Enthält die Zeichenfolge der strukturierten Abfragesprache, die für die angegebene externe Datenquelle ausgeführt werden soll, um den Satz von Datensätzen zurückzugeben, die in das Dokument importiert werden sollen, wenn der Seriendruckvorgang durchgeführt wird. Der Standardwert ist eine leere Zeichenfolge. |
| [ViewMergedData](../../aspose.words.settings/mailmergesettings/viewmergeddata/) { get; set; } | Gibt an, dass Microsoft Word die Daten aus der angegebenen externen Datenquelle anzeigt, in die Briefvorlagenfelder eingefügt wurden (z. B. Vorschau der zusammengeführten Daten). Der Standardwert ist`FALSCH` . |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Clear](../../aspose.words.settings/mailmergesettings/clear/)() | Löscht die Serienbriefeinstellungen so, dass beim Speichern des Dokuments keine Serienbriefeinstellungen gespeichert werden und es zu einem normalen Dokument wird. |
| [Clone](../../aspose.words.settings/mailmergesettings/clone/)() | Gibt einen tiefen Klon dieses Objekts zurück. |

### Bemerkungen

Sie können dieses Objekt verwenden, um eine Serienbriefdatenquelle für ein Dokument anzugeben, und diese Informationen (zusammen mit den verfügbaren Datenfeldern) werden in Microsoft Word angezeigt, wenn der Benutzer dieses Dokument öffnet. Oder Sie können dieses Objekt verwenden, um Serienbriefeinstellungen abzufragen die der Benutzer in Microsoft Word für dieses Dokument angegeben hat.

Normalerweise müssen Sie Objekte dieser Klasse nicht direkt erstellen, da die Serienbriefeinstellungen eines Dokuments immer über die verfügbar sind[`MailMergeSettings`](../../aspose.words/document/mailmergesettings/) Eigentum.

Um festzustellen, ob es sich bei diesem Dokument um ein Seriendruck-Hauptdokument handelt, überprüfen Sie den Wert von [`MainDocumentType`](./maindocumenttype/) Eigentum.

Um Serienbriefeinstellungen und Datenquelleninformationen aus einem Dokument zu entfernen, können Sie das [`Clear`](./clear/) Methode. Aspose.Words schreibt keine Serienbriefeinstellungen in ein Dokument, wenn die[`MainDocumentType`](./maindocumenttype/) Eigenschaft eingestellt istNotAMergeDocument oder die[`DataType`](./datatype/) Eigenschaft eingestellt istNone.

Der beste Weg, um zu lernen, wie man die Eigenschaften dieses Objekts verwendet, besteht darin, ein Dokument mit einer gewünschten -Datenquelle manuell in Microsoft Word zu erstellen und dieses Dokument dann mit Aspose.Words zu öffnen und die Eigenschaften von zu untersuchen[`MailMergeSettings`](../../aspose.words/document/mailmergesettings/) und[`Odso`](./odso/) Objekte. Dies ist ein guter Ansatz, wenn Sie beispielsweise lernen möchten, wie Sie eine Datenquelle programmgesteuert konfigurieren.

Aspose.Words behält Serienbriefinformationen beim Laden, Speichern und Konvertieren von Dokumenten zwischen verschiedenen Formaten bei, verwendet diese Informationen jedoch nicht, wenn es seinen eigenen Serienbrief mit dem durchführt[`MailMerge`](../../aspose.words.mailmerging/mailmerge/) Objekt.

### Beispiele

Zeigt, wie ein Seriendruck mit Daten aus einem Office-Datenquellenobjekt ausgeführt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");
builder.Writeln(": ");
builder.InsertField("MERGEFIELD Message", "<Message>");

// Erstellen Sie eine Datenquelle in Form einer ASCII-Datei, mit dem "|" Charakter
// fungiert als Trennzeichen, das Spalten trennt. Die erste Zeile enthält die Namen der drei Spalten,
// und jede nachfolgende Zeile ist eine Zeile mit ihren jeweiligen Werten.
string[] lines = { "FirstName|LastName|Message",
    "John|Doe|Hello! This message was created with Aspose Words mail merge." };
string dataSrcFilename = ArtifactsDir + "MailMerge.MailMergeSettings.DataSource.txt";

File.WriteAllLines(dataSrcFilename, lines);

MailMergeSettings settings = doc.MailMergeSettings;
settings.MainDocumentType = MailMergeMainDocumentType.MailingLabels;
settings.CheckErrors = MailMergeCheckErrors.Simulate;
settings.DataType = MailMergeDataType.Native;
settings.DataSource = dataSrcFilename;
settings.Query = "SELECT * FROM " + doc.MailMergeSettings.DataSource;
settings.LinkToQuery = true;
settings.ViewMergedData = true;

Assert.AreEqual(MailMergeDestination.Default, settings.Destination);
Assert.False(settings.DoNotSupressBlankLines);

Odso odso = settings.Odso;
odso.DataSource = dataSrcFilename;
odso.DataSourceType = OdsoDataSourceType.Text;
odso.ColumnDelimiter = '|';
odso.FirstRowContainsColumnNames = true;

Assert.AreNotSame(odso, odso.Clone());
Assert.AreNotSame(settings, settings.Clone());

// Beim Öffnen dieses Dokuments in Microsoft Word wird der Seriendruck ausgeführt, bevor der Inhalt angezeigt wird. 
doc.Save(ArtifactsDir + "MailMerge.MailMergeSettings.docx");
```

### Siehe auch

* namensraum [Aspose.Words.Settings](../../aspose.words.settings/)
* Montage [Aspose.Words](../../)


