---
title: Document.ExtractPages
second_title: Aspose.Words per .NET API Reference
description: Document metodo. Restituisce ilDocument oggetto che rappresenta lintervallo di pagine specificato.
type: docs
weight: 580
url: /it/net/aspose.words/document/extractpages/
---
## Document.ExtractPages method

Restituisce il[`Document`](../) oggetto che rappresenta l'intervallo di pagine specificato.

```csharp
public Document ExtractPages(int index, int count)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| index | Int32 | Indice in base zero della prima pagina da estrarre. |
| count | Int32 | Numero di pagine da estrarre. |

### Osservazioni

Il documento risultante dovrebbe assomigliare a quello in MS Word, come se avessimo eseguito "Stampa pagine specifiche" – la numerazione, intestazioni/piè di pagina e il layout delle tabelle incrociate verranno preservati. Ma a causa di un gran numero di sfumature, appare pur riducendo il numero di pagine, la corrispondenza completa del layout è un'attività complicata che richiede molto sforzo. A seconda della complessità del documento potrebbero esserci lievi differenze nel layout del contenuto del documento risultante rispetto al documento di origine. Qualsiasi feedback sarebbe essere molto apprezzato.

### Esempi

Mostra come ottenere un intervallo di pagine specificato dal documento.

```csharp
Document doc = new Document(MyDir + "Layout entities.docx");

doc = doc.ExtractPages(0, 2);

doc.Save(ArtifactsDir + "Document.ExtractPages.docx");
```

### Guarda anche

* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


