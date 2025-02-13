---
title: Enum JsonSimpleValueParseMode
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Reporting.JsonSimpleValueParseMode enumeración. Especifica un modo para analizar valores simples de JSON null boolean number integer y string mientras se carga JSON. Este modo no afecta el análisis de los valores de fecha y hora.
type: docs
weight: 4440
url: /es/net/aspose.words.reporting/jsonsimplevalueparsemode/
---
## JsonSimpleValueParseMode enumeration

Especifica un modo para analizar valores simples de JSON (null, boolean, number, integer y string) mientras se carga JSON. Este modo no afecta el análisis de los valores de fecha y hora.

```csharp
public enum JsonSimpleValueParseMode
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Loose | `0` | Especifica el modo en el que los tipos de valores simples JSON se determinan al analizar sus representaciones de cadena. Por ejemplo, el tipo de 'prop' del fragmento de código JSON '{ prop: "123" }' se determina como entero en este modo. |
| Strict | `1` | Especifica el modo en el que los tipos de valores simples JSON se determinan a partir de la propia notación JSON. Por ejemplo, el tipo de 'prop' del fragmento JSON '{ prop: "123" }' se determina como cadena en este modo. |

### Ver también

* espacio de nombres [Aspose.Words.Reporting](../../aspose.words.reporting/)
* asamblea [Aspose.Words](../../)


