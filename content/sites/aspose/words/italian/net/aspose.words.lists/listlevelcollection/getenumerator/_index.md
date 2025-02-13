---
title: ListLevelCollection.GetEnumerator
second_title: Aspose.Words per .NET API Reference
description: ListLevelCollection metodo. Ottiene loggetto enumeratore che enumera i livelli in questo elenco.
type: docs
weight: 30
url: /it/net/aspose.words.lists/listlevelcollection/getenumerator/
---
## ListLevelCollection.GetEnumerator method

Ottiene l'oggetto enumeratore che enumera i livelli in questo elenco.

```csharp
public IEnumerator<ListLevel> GetEnumerator()
```

### Esempi

Mostra metodi avanzati di personalizzazione delle etichette degli elenchi.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Un elenco ci consente di organizzare e decorare insiemi di paragrafi con simboli e rientri prefissi.
// Possiamo creare liste nidificate aumentando il livello di rientro. 
// Possiamo iniziare e terminare un elenco utilizzando la proprietà "ListFormat" di un generatore di documenti. 
// Ogni paragrafo che aggiungiamo tra l'inizio e la fine di un elenco diventerà un elemento nell'elenco.
List list = doc.Lists.Add(ListTemplate.NumberDefault);

// Le etichette di livello 1 verranno formattate in base allo stile di paragrafo "Intestazione 1" e avranno un prefisso.
// Sembreranno "Appendice A", "Appendice B"...
list.ListLevels[0].NumberFormat = "Appendix \x0000";
list.ListLevels[0].NumberStyle = NumberStyle.UppercaseLetter;
list.ListLevels[0].LinkedStyle = doc.Styles["Heading 1"];

// Le etichette di livello 2 visualizzeranno i numeri correnti del primo e del secondo livello di elenco e avranno degli zeri iniziali.
// Se il primo livello di elenco è a 1, le etichette dell'elenco da questi appariranno come "Sezione (1.01)", "Sezione (1.02)"...
list.ListLevels[1].NumberFormat = "Section (\x0000.\x0001)";
list.ListLevels[1].NumberStyle = NumberStyle.LeadingZero;

// Nota che il livello superiore usa la numerazione in lettere maiuscole.
// Possiamo impostare la proprietà "IsLegal" per utilizzare i numeri arabi per i livelli di elenco più alti.
list.ListLevels[1].IsLegal = true;
list.ListLevels[1].RestartAfterLevel = 0;

// Le etichette di livello 3 saranno numeri romani maiuscoli con un prefisso e un suffisso e ricominceranno a ogni voce di livello 1 dell'elenco.
// Queste etichette di elenco saranno simili a "-I-", "-II-"...
list.ListLevels[2].NumberFormat = "-\x0002-";
list.ListLevels[2].NumberStyle = NumberStyle.UppercaseRoman;
list.ListLevels[2].RestartAfterLevel = 1;

// Crea in grassetto le etichette di tutti i livelli di elenco.
foreach (ListLevel level in list.ListLevels)
    level.Font.Bold = true;

// Applica la formattazione dell'elenco al paragrafo corrente.
builder.ListFormat.List = list;

// Crea voci di elenco che visualizzeranno tutti e tre i livelli di elenco.
for (int n = 0; n < 2; n++)
{
    for (int i = 0; i < 3; i++)
    {
        builder.ListFormat.ListLevelNumber = i;
        builder.Writeln("Level " + i);
    }
}

builder.ListFormat.RemoveNumbers();

doc.Save(ArtifactsDir + "Lists.CreateListRestartAfterHigher.docx");
```

### Guarda anche

* class [ListLevel](../../listlevel/)
* class [ListLevelCollection](../)
* spazio dei nomi [Aspose.Words.Lists](../../listlevelcollection/)
* assemblea [Aspose.Words](../../../)


