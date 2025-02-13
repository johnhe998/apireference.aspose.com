---
title: JsonDataLoadOptions.ExactDateTimeParseFormats
second_title: Aspose.Words für .NET-API-Referenz
description: JsonDataLoadOptions eigendom. Ruft genaue Formate für die Analyse von JSONDatums/Uhrzeitwerten beim Laden von JSON ab oder legt diese fest. Die Voreinstellung ist Null .
type: docs
weight: 30
url: /de/net/aspose.words.reporting/jsondataloadoptions/exactdatetimeparseformats/
---
## JsonDataLoadOptions.ExactDateTimeParseFormats property

Ruft genaue Formate für die Analyse von JSON-Datums-/Uhrzeitwerten beim Laden von JSON ab oder legt diese fest. Die Voreinstellung ist **Null** .

```csharp
public IEnumerable<string> ExactDateTimeParseFormats { get; set; }
```

### Bemerkungen

Zeichenfolgen, die mit dem Microsoft® JSON-Datums-/Uhrzeitformat codiert sind (z. B. „/Date(1224043200000)/“), werden immer als Datums-/Uhrzeitwerte erkannt, unabhängig von einem Wert dieser Eigenschaft. Die Eigenschaft definiert zusätzliche -Formate, die beim Analysieren von Datums- und Uhrzeitwerten aus Zeichenfolgen auf folgende Weise verwendet werden:

* Wann`ExactDateTimeParseFormats` ist **Null** , das ISO-8601-Format und alle Datums-/Zeitformate , die für die aktuellen Kulturen Englisch USA und Englisch Neuseeland unterstützt werden, werden zusätzlich in der genannten Reihenfolge verwendet.
* Wann`ExactDateTimeParseFormats` Zeichenfolgen enthält, werden sie als zusätzliche date-time -Formate unter Verwendung der aktuellen Kultur verwendet.
* Wann`ExactDateTimeParseFormats` leer ist, werden keine zusätzlichen Datums-Zeit-Formate verwendet.

### Siehe auch

* class [JsonDataLoadOptions](../)
* namensraum [Aspose.Words.Reporting](../../jsondataloadoptions/)
* Montage [Aspose.Words](../../../)


