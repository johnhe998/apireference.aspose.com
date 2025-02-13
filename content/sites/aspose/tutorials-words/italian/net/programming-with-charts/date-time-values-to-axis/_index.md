---
title: Aggiungi i valori di data e ora all'asse di un grafico
linktitle: Aggiungi i valori di data e ora all'asse di un grafico
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiungere valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/date-time-values-to-axis/
---

Questo tutorial spiega come aggiungere valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e Word Processing con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si desidera salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un nuovo documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` opporsi a lavorare con il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire e configurare una forma del grafico
 Inserisci una forma di grafico nel documento usando il`InsertChart` metodo del`DocumentBuilder` oggetto. Impostare il tipo e le dimensioni del grafico desiderati.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Passaggio 4: aggiungere dati al grafico
Aggiungi dati alla serie di grafici, inclusi i valori di data e ora.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Passaggio 5: configurare l'asse
Configurare l'asse X del grafico per visualizzare i valori di data e ora.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Passaggio 6: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Codice sorgente di esempio per i valori di data e ora sull'asse utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Imposta le unità principali su una settimana e le unità secondarie su un giorno.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Questo codice di esempio crea un nuovo documento di Word, inserisce un istogramma con valori di data e ora sull'asse X e salva il documento nella directory specificata.

## Conclusione
In questo tutorial, hai imparato come aggiungere valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo-passo, puoi creare un grafico, aggiungere valori di data e ora alla serie e configurare l'asse per visualizzare i valori di data e ora in modo accurato. Aspose.Words per .NET offre un potente set di funzionalità per l'elaborazione di testi con grafici nei documenti di Word, consentendo di rappresentare e visualizzare i dati con valori di data e ora in modo efficace.

### Domande frequenti

#### Q1. Posso aggiungere valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET?
Sì, con Aspose.Words per .NET, puoi aggiungere e visualizzare i valori di data e ora sull'asse di un grafico in un documento di Word. Aspose.Words fornisce API e funzionalità per lavorare con vari tipi di grafici e personalizzarne l'aspetto, inclusa la gestione dei valori di data e ora sull'asse.

#### D2. Come posso aggiungere valori di data e ora alla serie di grafici?
 Per aggiungere valori di data e ora alla serie di grafici, è possibile utilizzare il file`Add`metodo della serie del grafico. Fornisci una matrice di valori di data e ora come dati di categoria (asse X), insieme ai valori di serie corrispondenti. Ciò consente di tracciare punti dati con valori di data e ora sul grafico.

#### D3. Come posso configurare l'asse per visualizzare i valori di data e ora?
 È possibile configurare l'asse del grafico per visualizzare i valori di data e ora impostando le proprietà appropriate. Ad esempio, è possibile specificare i valori minimo e massimo per l'asse utilizzando il`Scaling.Minimum` E`Scaling.Maximum` proprietà, rispettivamente. Inoltre, è possibile impostare le unità principali e secondarie per definire l'intervallo e le tacche per l'asse.
