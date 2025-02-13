---
title: Class OleFormat
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.OleFormat classe. Fornisce laccesso ai dati di un oggetto OLE o di un controllo ActiveX.
type: docs
weight: 1020
url: /it/net/aspose.words.drawing/oleformat/
---
## OleFormat class

Fornisce l'accesso ai dati di un oggetto OLE o di un controllo ActiveX.

```csharp
public class OleFormat
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [AutoUpdate](../../aspose.words.drawing/oleformat/autoupdate/) { get; set; } | Specifica se il collegamento all'oggetto OLE viene aggiornato automaticamente o meno in Microsoft Word. |
| [Clsid](../../aspose.words.drawing/oleformat/clsid/) { get; } | Ottiene il CLSID dell'oggetto OLE. |
| [IconCaption](../../aspose.words.drawing/oleformat/iconcaption/) { get; } | Ottiene la didascalia dell'icona dell'oggetto OLE. |
| [IsLink](../../aspose.words.drawing/oleformat/islink/) { get; } | Restituisce true se l'oggetto OLE è collegato (quando[`SourceFullName`](./sourcefullname/) è specificato). |
| [IsLocked](../../aspose.words.drawing/oleformat/islocked/) { get; set; } | Specifica se il collegamento all'oggetto OLE è bloccato dagli aggiornamenti. |
| [OleControl](../../aspose.words.drawing/oleformat/olecontrol/) { get; } | Ottiene[`OleControl`](./olecontrol/) oggetti se questo oggetto OLE è un controllo ActiveX. Altrimenti questa proprietà è null. |
| [OleIcon](../../aspose.words.drawing/oleformat/oleicon/) { get; } | Ottiene l'aspetto di disegno dell'oggetto OLE. quando **VERO** , l'oggetto OLE viene visualizzato come un'icona. Quando **falso** , l'oggetto OLE viene visualizzato come contenuto. |
| [OlePackage](../../aspose.words.drawing/oleformat/olepackage/) { get; } | Fornisci l'accesso a[`OlePackage`](../olepackage/) se l'oggetto OLE è un pacchetto OLE. Restituisce null in caso contrario. |
| [ProgId](../../aspose.words.drawing/oleformat/progid/) { get; set; } | Ottiene o imposta il ProgID dell'oggetto OLE. |
| [SourceFullName](../../aspose.words.drawing/oleformat/sourcefullname/) { get; set; } | Ottiene o imposta il percorso e il nome del file di origine per l'oggetto OLE collegato. |
| [SourceItem](../../aspose.words.drawing/oleformat/sourceitem/) { get; set; } | Ottiene o imposta una stringa utilizzata per identificare la parte del file di origine che viene collegata. |
| [SuggestedExtension](../../aspose.words.drawing/oleformat/suggestedextension/) { get; } | Ottiene l'estensione del file suggerita per l'oggetto incorporato corrente se si desidera salvarlo in un file. |
| [SuggestedFileName](../../aspose.words.drawing/oleformat/suggestedfilename/) { get; } | Ottiene il nome file suggerito per l'oggetto incorporato corrente se si desidera salvarlo in un file. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [GetOleEntry](../../aspose.words.drawing/oleformat/getoleentry/)(string) | Ottiene l'immissione dei dati dell'oggetto OLE. |
| [GetRawData](../../aspose.words.drawing/oleformat/getrawdata/)() | Ottiene i dati grezzi dell'oggetto OLE. |
| [Save](../../aspose.words.drawing/oleformat/save/#save)(Stream) | Salva i dati dell'oggetto incorporato nel flusso specificato. |
| [Save](../../aspose.words.drawing/oleformat/save/#save_1)(string) | Salva i dati dell'oggetto incorporato in un file con il nome specificato. |

### Osservazioni

Utilizzare il[`OleFormat`](../shape/oleformat/) proprietà per accedere ai dati di un oggetto OLE. Non si creano istanze di`OleFormat` classe direttamente.

### Esempi

Mostra come estrarre gli oggetti OLE incorporati nei file.

```csharp
Document doc = new Document(MyDir + "OLE spreadsheet.docm");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

// L'oggetto OLE nella prima forma è un foglio di calcolo di Microsoft Excel.
OleFormat oleFormat = shape.OleFormat;

Assert.AreEqual("Excel.Sheet.12", oleFormat.ProgId);

// Il nostro oggetto non si aggiorna automaticamente né è bloccato dagli aggiornamenti.
Assert.False(oleFormat.AutoUpdate);
Assert.AreEqual(false, oleFormat.IsLocked);

// Se intendiamo salvare l'oggetto OLE in un file nel file system locale,
// possiamo utilizzare la proprietà "SuggestedExtension" per determinare quale estensione di file applicare al file.
Assert.AreEqual(".xlsx", oleFormat.SuggestedExtension);

// Di seguito sono riportati due modi per salvare un oggetto OLE in un file nel file system locale.
// 1 - Salvalo tramite uno stream:
using (FileStream fs = new FileStream(ArtifactsDir + "OLE spreadsheet extracted via stream" + oleFormat.SuggestedExtension, FileMode.Create))
{
    oleFormat.Save(fs);
}

// 2 - Salvalo direttamente in un nome file:
oleFormat.Save(ArtifactsDir + "OLE spreadsheet saved directly" + oleFormat.SuggestedExtension);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Drawing](../../aspose.words.drawing/)
* assemblea [Aspose.Words](../../)


