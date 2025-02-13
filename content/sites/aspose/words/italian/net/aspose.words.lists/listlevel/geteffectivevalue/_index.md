---
title: ListLevel.GetEffectiveValue
second_title: Aspose.Words per .NET API Reference
description: ListLevel metodo. Riporta la rappresentazione di stringa delListLevel oggetto per lindice specificato della voce di elenco. I parametri specificano ilNumberStyle e un formato opzionale string utilizzato quandoCustom è specificato.
type: docs
weight: 190
url: /it/net/aspose.words.lists/listlevel/geteffectivevalue/
---
## ListLevel.GetEffectiveValue method

Riporta la rappresentazione di stringa del[`ListLevel`](../) oggetto per l'indice specificato della voce di elenco. I parametri specificano il[`NumberStyle`](../../../aspose.words/numberstyle/) e un formato opzionale string utilizzato quandoCustom è specificato.

```csharp
public static string GetEffectiveValue(int index, NumberStyle numberStyle, 
    string customNumberStyleFormat)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| index | Int32 | L'indice della voce dell'elenco (deve essere compreso tra 1 e 32767). |
| numberStyle | NumberStyle | Il[`NumberStyle`](../../../aspose.words/numberstyle/) del[`ListLevel`](../) oggetto. |
| customNumberStyleFormat | String | La stringa di formato opzionale utilizzata quandoCustom è specificato (ad es. "a, ç, ĝ, ..."). Negli altri casi, questo parametro deve essere nullo o vuoto. |

### Valore di ritorno

La rappresentazione di stringa di[`ListLevel`](../) oggetto, descritto dal parametro numberStyle e dal parametro customNumberStyleFormat, nella voce di elenco nella posizione determinata dal parametro index.

### Eccezioni

| eccezione | condizione |
| --- | --- |
| ArgumentException | customNumberStyleFormat è nullo o vuoto quando numberStyle è personalizzato.-o-- customNumberStyleFormat non è nullo o vuoto quando numberStyle non è personalizzato.-o-- customNumberStyleFormat non è valido. |
| ArgumentOutOfRangeException | l'indice è fuori intervallo. |

### Esempi

Mostra come ottenere il formato per un elenco con lo stile numerico personalizzato.

```csharp
Document doc = new Document(MyDir + "List with leading zero.docx");

ListLevel listLevel = doc.FirstSection.Body.Paragraphs[0].ListFormat.ListLevel;

string customNumberStyleFormat = string.Empty;

if (listLevel.NumberStyle == NumberStyle.Custom)
    customNumberStyleFormat = listLevel.CustomNumberStyleFormat;

Assert.AreEqual("001, 002, 003, ...", customNumberStyleFormat);

// Possiamo ottenere il valore per l'indice specificato dell'elemento dell'elenco.
Assert.AreEqual("iv", ListLevel.GetEffectiveValue(4, NumberStyle.LowercaseRoman, null));
Assert.AreEqual("005", ListLevel.GetEffectiveValue(5, NumberStyle.Custom, customNumberStyleFormat));
```

### Guarda anche

* enum [NumberStyle](../../../aspose.words/numberstyle/)
* class [ListLevel](../)
* spazio dei nomi [Aspose.Words.Lists](../../listlevel/)
* assemblea [Aspose.Words](../../../)


