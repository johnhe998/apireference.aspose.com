---
title: Enum ListTrailingCharacter
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Lists.ListTrailingCharacter enum. Specifica il carattere che separa letichetta dellelenco dal testo del paragrafo.
type: docs
weight: 3340
url: /it/net/aspose.words.lists/listtrailingcharacter/
---
## ListTrailingCharacter enumeration

Specifica il carattere che separa l'etichetta dell'elenco dal testo del paragrafo.

```csharp
public enum ListTrailingCharacter
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Tab | `0` | Viene inserito un carattere di tabulazione tra l'etichetta dell'elenco e il testo del paragrafo. |
| Space | `1` | Viene inserito uno spazio tra l'etichetta dell'elenco e il testo del paragrafo. |
| Nothing | `2` | Non è presente alcun carattere separatore tra l'etichetta dell'elenco e il testo del paragrafo. |

### Osservazioni

Usato come valore per il[`TrailingCharacter`](../listlevel/trailingcharacter/) proprietà.

### Esempi

Mostra come applicare la formattazione personalizzata dell'elenco ai paragrafi quando si utilizza DocumentBuilder.

```csharp
Document doc = new Document();

// Un elenco ci consente di organizzare e decorare insiemi di paragrafi con simboli e rientri prefissi.
// Possiamo creare liste nidificate aumentando il livello di rientro. 
// Possiamo iniziare e terminare un elenco utilizzando la proprietà "ListFormat" di un generatore di documenti. 
// Ogni paragrafo che aggiungiamo tra l'inizio e la fine di un elenco diventerà un elemento nell'elenco.
// Crea un elenco da un modello di Microsoft Word e personalizza i primi due livelli di elenco.
List list = doc.Lists.Add(ListTemplate.NumberDefault);

ListLevel listLevel = list.ListLevels[0];
listLevel.Font.Color = Color.Red;
listLevel.Font.Size = 24;
listLevel.NumberStyle = NumberStyle.OrdinalText;
listLevel.StartAt = 21;
listLevel.NumberFormat = "\x0000";

listLevel.NumberPosition = -36;
listLevel.TextPosition = 144;
listLevel.TabPosition = 144;

listLevel = list.ListLevels[1];
listLevel.Alignment = ListLevelAlignment.Right;
listLevel.NumberStyle = NumberStyle.Bullet;
listLevel.Font.Name = "Wingdings";
listLevel.Font.Color = Color.Blue;
listLevel.Font.Size = 24;

// Questo valore NumberFormat creerà simboli di elenchi puntati a forma di stella.
listLevel.NumberFormat = "\xf0af";
listLevel.TrailingCharacter = ListTrailingCharacter.Space;
listLevel.NumberPosition = 144;

// Crea paragrafi e applica loro entrambi i livelli di elenco della nostra formattazione personalizzata.
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.List = list;
builder.Writeln("The quick brown fox...");
builder.Writeln("The quick brown fox...");

builder.ListFormat.ListIndent();
builder.Writeln("jumped over the lazy dog.");
builder.Writeln("jumped over the lazy dog.");

builder.ListFormat.ListOutdent();
builder.Writeln("The quick brown fox...");

builder.ListFormat.RemoveNumbers();

builder.Document.Save(ArtifactsDir + "Lists.CreateCustomList.docx");
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Lists](../../aspose.words.lists/)
* assemblea [Aspose.Words](../../)


