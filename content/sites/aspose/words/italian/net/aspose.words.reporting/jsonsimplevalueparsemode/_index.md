---
title: Enum JsonSimpleValueParseMode
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Reporting.JsonSimpleValueParseMode enum. Specifica una modalità per lanalisi dei valori JSON semplici null booleano numero intero e stringa durante il caricamento di JSON. Tale modalità non influisce sullanalisi dei valori di data e ora.
type: docs
weight: 4440
url: /it/net/aspose.words.reporting/jsonsimplevalueparsemode/
---
## JsonSimpleValueParseMode enumeration

Specifica una modalità per l'analisi dei valori JSON semplici (null, booleano, numero, intero e stringa) durante il caricamento di JSON. Tale modalità non influisce sull'analisi dei valori di data e ora.

```csharp
public enum JsonSimpleValueParseMode
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Loose | `0` | Specifica la modalità in cui i tipi di valori JSON semplici vengono determinati dopo l'analisi delle relative rappresentazioni di stringa. Ad esempio, il tipo di 'prop' dal frammento di codice JSON '{ prop: "123" }' è determinato come intero in questa modalità. |
| Strict | `1` | Specifica la modalità in cui i tipi di valori JSON semplici sono determinati dalla notazione JSON stessa. Ad esempio, il tipo di 'prop' dallo snippet JSON '{ prop: "123" }' è determinato come stringa in questa modalità. |

### Guarda anche

* spazio dei nomi [Aspose.Words.Reporting](../../aspose.words.reporting/)
* assemblea [Aspose.Words](../../)


