---
title: KnownTypeSet.Add
second_title: Aspose.Words per .NET API Reference
description: KnownTypeSet metodo. Aggiunge il specificatoType opporsi allinsieme. TiriArgumentException in i seguenti casi
type: docs
weight: 20
url: /it/net/aspose.words.reporting/knowntypeset/add/
---
## KnownTypeSet.Add method

Aggiunge il specificatoType opporsi all'insieme. TiriArgumentException in i seguenti casi:

-*type* è zero.

-*type* rappresenta un tipo vuoto.

-*type* rappresenta un tipo invisibile, cioè un tipo non pubblico o un tipo nidificato pubblico che ha un tipo esterno non pubblico.

-*type* rappresenta un tipo generico.

-*type* rappresenta un tipo di matrice.

-*type* è già stato aggiunto al set.

```csharp
public void Add(Type type)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| type | Type | UNType oggetto da aggiungere. |

### Guarda anche

* class [KnownTypeSet](../)
* spazio dei nomi [Aspose.Words.Reporting](../../knowntypeset/)
* assemblea [Aspose.Words](../../../)


