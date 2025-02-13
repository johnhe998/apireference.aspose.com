---
title: Class JsonDataSource
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Reporting.JsonDataSource klas. Bietet Zugriff auf Daten einer JSONDatei oder eines Streams zur Verwendung in einem Bericht.
type: docs
weight: 4430
url: /de/net/aspose.words.reporting/jsondatasource/
---
## JsonDataSource class

Bietet Zugriff auf Daten einer JSON-Datei oder eines Streams zur Verwendung in einem Bericht.

```csharp
public class JsonDataSource
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [JsonDataSource](jsondatasource/#constructor)(Stream) | Erstellt eine neue Datenquelle mit Daten aus einem JSON-Stream unter Verwendung von Standardoptionen zum Analysieren von JSON-Daten. |
| [JsonDataSource](jsondatasource/#constructor_2)(string) | Erstellt eine neue Datenquelle mit Daten aus einer JSON-Datei unter Verwendung von Standardoptionen zum Analysieren von JSON-Daten. |
| [JsonDataSource](jsondatasource/#constructor_1)(Stream, JsonDataLoadOptions) | Erstellt eine neue Datenquelle mit Daten aus einem JSON-Stream unter Verwendung der angegebenen Optionen zum Parsen von JSON-Daten. |
| [JsonDataSource](jsondatasource/#constructor_3)(string, JsonDataLoadOptions) | Erstellt eine neue Datenquelle mit Daten aus einer JSON-Datei unter Verwendung der angegebenen Optionen zum Parsen von JSON-Daten. |

### Bemerkungen

Um beim Generieren eines Berichts auf Daten der entsprechenden Datei oder des Streams zuzugreifen, übergeben Sie eine Instanz dieser Klasse als an eine der Datenquellen[`ReportingEngine`](../reportingengine/) .BuildReport-Überladungen.

Wenn in Vorlagendokumenten ein JSON-Element der obersten Ebene ein Array ist, a`JsonDataSource` -Instanz sollte be genauso behandelt werden, als wäre sie eineDataTable Instanz. Wenn ein JSON-Element der obersten Ebene ein Objekt ist, a`JsonDataSource` Beispiel sollte genauso behandelt werden, als wäre es aDataRow Instanz. Weitere Informationen finden Sie in der Referenz zur Vorlagensyntax (https://docs.aspose.com/display/wordsnet/Template+Syntax).

In Vorlagendokumenten können Sie mit typisierten Werten von JSON-Elementen arbeiten. Der Einfachheit halber ersetzt die Engine den Satz der einfachen JSON-Typen durch den folgenden:

* Nullable
* Nullable
* Nullable
* Nullable
* String

Die Engine erkennt automatisch Werte der zusätzlichen Typen anhand ihrer JSON-Darstellungen.

Um das Standardverhalten beim Laden von JSON-Daten zu überschreiben, initialisieren und übergeben Sie a[`JsonDataLoadOptions`](../jsondataloadoptions/)instance zu einem Konstruktor dieser Klasse.

### Siehe auch

* namensraum [Aspose.Words.Reporting](../../aspose.words.reporting/)
* Montage [Aspose.Words](../../)


