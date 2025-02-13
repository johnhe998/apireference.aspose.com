---
title: Class CsvDataSource
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Reporting.CsvDataSource klas. Bietet Zugriff auf Daten einer CSVDatei oder eines Streams zur Verwendung in einem Bericht.
type: docs
weight: 4410
url: /de/net/aspose.words.reporting/csvdatasource/
---
## CsvDataSource class

Bietet Zugriff auf Daten einer CSV-Datei oder eines Streams zur Verwendung in einem Bericht.

```csharp
public class CsvDataSource
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [CsvDataSource](csvdatasource/#constructor)(Stream) | Erstellt eine neue Datenquelle mit Daten aus einem CSV-Stream unter Verwendung von Standardoptionen zum Analysieren von CSV-Daten. |
| [CsvDataSource](csvdatasource/#constructor_2)(string) | Erstellt eine neue Datenquelle mit Daten aus einer CSV-Datei unter Verwendung von Standardoptionen zum Analysieren von CSV-Daten. |
| [CsvDataSource](csvdatasource/#constructor_1)(Stream, CsvDataLoadOptions) | Erstellt eine neue Datenquelle mit Daten aus einem CSV-Stream unter Verwendung der angegebenen Optionen zum Parsen von CSV-Daten. |
| [CsvDataSource](csvdatasource/#constructor_3)(string, CsvDataLoadOptions) | Erstellt eine neue Datenquelle mit Daten aus einer CSV-Datei unter Verwendung der angegebenen Optionen zum Parsen von CSV-Daten. |

### Bemerkungen

Um beim Generieren eines Berichts auf Daten der entsprechenden Datei oder des Streams zuzugreifen, übergeben Sie eine Instanz dieser Klasse als an eine der Datenquellen[`ReportingEngine`](../reportingengine/) .BuildReport-Überladungen.

In Vorlagendokumenten a`CsvDataSource` Instanz sollte genauso behandelt werden, als wäre es aDataTable Instanz. Weitere Informationen finden Sie in der Referenz zur Vorlagensyntax (https://docs.aspose.com/display/wordsnet/Template+Syntax).

Datentypen von kommagetrennten Werten werden automatisch anhand ihrer Zeichenfolgendarstellung bestimmt. In template -Dokumenten können Sie also mit eingegebenen Werten statt nur mit Zeichenfolgen arbeiten. Die Engine kann automatisch -Werte der folgenden Typen erkennen:

* Nullable
* Nullable
* Nullable
* Nullable
* String

Beachten Sie, dass für eine funktionierende automatische Erkennung von Datentypen Zeichenfolgendarstellungen von kommagetrennten Werten mit invarianten Kultureinstellungen gebildet werden sollten.

Um das Standardverhalten beim Laden von CSV-Daten zu überschreiben, initialisieren und übergeben Sie a[`CsvDataLoadOptions`](../csvdataloadoptions/)instance zu einem Konstruktor dieser Klasse.

### Siehe auch

* namensraum [Aspose.Words.Reporting](../../aspose.words.reporting/)
* Montage [Aspose.Words](../../)


