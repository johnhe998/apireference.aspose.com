---
title: Enum AxisBuiltInUnit
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.Charts.AxisBuiltInUnit enum. Specifica le unità di visualizzazione per un asse.
type: docs
weight: 510
url: /it/net/aspose.words.drawing.charts/axisbuiltinunit/
---
## AxisBuiltInUnit enumeration

Specifica le unità di visualizzazione per un asse.

```csharp
public enum AxisBuiltInUnit
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | Specifica i valori sul grafico da visualizzare così com'è. |
| Custom | `1` | Specifica che i valori sul grafico devono essere divisi per un divisore definito dall'utente. Questo valore non è supportato dai nuovi tipi di grafici di MS Office 2016. |
| Billions | `2` | Specifica che i valori sul grafico devono essere divisi per 1.000.000.000. |
| HundredMillions | `3` | Specifica che i valori sul grafico devono essere divisi per 100.000.000. |
| Hundreds | `4` | Specifica che i valori sul grafico devono essere divisi per 100. |
| HundredThousands | `5` | Specifica che i valori sul grafico devono essere divisi per 100.000. |
| Millions | `6` | Specifica che i valori sul grafico devono essere divisi per 1.000.000. |
| TenMillions | `7` | Specifica che i valori sul grafico devono essere divisi per 10.000.000. |
| TenThousands | `8` | Specifica che i valori sul grafico devono essere divisi per 10.000. |
| Thousands | `9` | Specifica che i valori sul grafico devono essere divisi per 1.000. |
| Trillions | `10` | Specifica che i valori sul grafico devono essere divisi per 1.000.000.000.0000. |
| Percentage | `11` | Specifica che i valori sul grafico devono essere divisi per 0,01. Questo valore è supportato solo dai nuovi tipi chart di MS Office 2016. |

### Esempi

Mostra come manipolare i segni di graduazione e i valori visualizzati di un asse del grafico.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Y-Values", chart.Series[0].Name);

// Imposta i segni di graduazione minori dell'asse Y in modo che puntino lontano dall'area del tracciato,
// e i segni di graduazione principali per attraversare l'asse.
ChartAxis axis = chart.AxisY;
axis.MajorTickMark = AxisTickMark.Cross;
axis.MinorTickMark = AxisTickMark.Outside;

// Imposta l'asse Y in modo che mostri un tick maggiore ogni 10 unità e un tick minore ogni 1 unità.
axis.MajorUnit = 10;
axis.MinorUnit = 1;

// Imposta i limiti dell'asse Y su -10 e 20.
// Questo asse Y ora visualizzerà 4 segni di graduazione principali e 27 segni di graduazione minori.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(20);

// Per l'asse X, imposta i segni di graduazione principali ogni 10 unità,
// ogni segno di spunta minore a 2,5 unità.
axis = chart.AxisX;
axis.MajorUnit = 10;
axis.MinorUnit = 2.5;

// Configura entrambi i tipi di segni di graduazione in modo che appaiano all'interno dell'area del grafico.
axis.MajorTickMark = AxisTickMark.Inside;
axis.MinorTickMark = AxisTickMark.Inside;

// Imposta i limiti dell'asse X in modo che l'asse X copra 5 segni di graduazione principali e 12 segni di graduazione minori.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(30);
axis.TickLabelAlignment = ParagraphAlignment.Right;

Assert.AreEqual(1, axis.TickLabelSpacing);

// Imposta le etichette di spunta per visualizzare il loro valore in milioni.
axis.DisplayUnit.Unit = AxisBuiltInUnit.Millions;

// Possiamo impostare un valore più specifico in base al quale le etichette di spunta visualizzeranno i loro valori.
// Questa affermazione è equivalente a quella sopra.
axis.DisplayUnit.CustomUnit = 1000000;
doc.Save(ArtifactsDir + "Charts.AxisDisplayUnit.docx");
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* assemblea [Aspose.Words](../../)


