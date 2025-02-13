---
title: Enum JsonSimpleValueParseMode
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Reporting.JsonSimpleValueParseMode opsomming. Gibt einen Modus zum Analysieren einfacher JSONWerte Null Boolean Zahl Ganzzahl und Zeichenfolge beim Laden von JSON an. Ein solcher Modus wirkt sich nicht auf die Analyse von Datums und Uhrzeitwerten aus.
type: docs
weight: 4440
url: /de/net/aspose.words.reporting/jsonsimplevalueparsemode/
---
## JsonSimpleValueParseMode enumeration

Gibt einen Modus zum Analysieren einfacher JSON-Werte (Null, Boolean, Zahl, Ganzzahl und Zeichenfolge) beim Laden von JSON an. Ein solcher Modus wirkt sich nicht auf die Analyse von Datums- und Uhrzeitwerten aus.

```csharp
public enum JsonSimpleValueParseMode
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Loose | `0` | Gibt den Modus an, in dem Typen von einfachen JSON-Werten beim Analysieren ihrer Zeichenfolgendarstellungen bestimmt werden. Beispielsweise wird der Typ von „Prop“ aus dem JSON-Snippet „{ Prop: „123“ }“ in diesem Modus als Ganzzahl bestimmt. |
| Strict | `1` | Gibt den Modus an, in dem Typen von einfachen JSON-Werten aus der JSON-Notation selbst bestimmt werden. Beispielsweise wird der Typ von 'prop' aus dem JSON-Snippet '{ prop: "123" }' in diesem Modus als Zeichenfolge bestimmt. |

### Siehe auch

* namensraum [Aspose.Words.Reporting](../../aspose.words.reporting/)
* Montage [Aspose.Words](../../)


