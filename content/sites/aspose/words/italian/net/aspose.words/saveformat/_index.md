---
title: Enum SaveFormat
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.SaveFormat enum. Indica il formato in cui è salvato il documento.
type: docs
weight: 4580
url: /it/net/aspose.words/saveformat/
---
## SaveFormat enumeration

Indica il formato in cui è salvato il documento.

```csharp
public enum SaveFormat
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Unknown | `0` | Valore predefinito, non valido per il formato file. |
| Doc | `10` | Salva il documento nel formato documento Microsoft Word 97 - 2007. |
| Dot | `11` | Salva il documento nel formato modello Microsoft Word 97 - 2007. |
| Docx | `20` | Salva il documento come documento Office Open XML WordprocessingML (senza macro). |
| Docm | `21` | Salva il documento come documento Office Open XML WordprocessingML con abilitazione macro. |
| Dotx | `22` | Salva il documento come modello WordprocessingML di Office Open XML (senza macro). |
| Dotm | `23` | Salva il documento come modello Office Open XML WordprocessingML con abilitazione macro. |
| FlatOpc | `24` | Salva il documento come un WordprocessingML di Office Open XML archiviato in un file XML flat anziché in un pacchetto ZIP. |
| FlatOpcMacroEnabled | `25` | Salva il documento come documento Office Open XML WordprocessingML con abilitazione macro archiviato in un file XML piatto anziché in un pacchetto ZIP. |
| FlatOpcTemplate | `26` | Salva il documento come modello WordprocessingML di Office Open XML (senza macro) archiviato in un file XML piatto anziché in un pacchetto ZIP. |
| FlatOpcTemplateMacroEnabled | `27` | Salva il documento come modello Office Open XML WordprocessingML con abilitazione macro archiviato in un file XML semplice anziché in un pacchetto ZIP. |
| Rtf | `30` | Salva il documento nel formato RTF. Tutti i caratteri superiori a 7 bit vengono sottoposti a escape come caratteri esadecimali o Unicode. |
| WordML | `31` | Salva il documento nel formato WordprocessingML di Microsoft Word 2003. |
| Pdf | `40` | Salva il documento in formato PDF (Adobe Portable Document). |
| Xps | `41` | Salva il documento nel formato XPS (XML Paper Specification). |
| XamlFixed | `42` | Salva il documento nel formato Extensible Application Markup Language (XAML) come documento fisso. |
| Svg | `44` | Salva il documento nel formato Svg (Scalable Vector Graphics). |
| HtmlFixed | `45` | Salva il documento in formato HTML utilizzando elementi posizionati in modo assoluto |
| OpenXps | `46` | Salva il documento nel formato OpenXPS (Ecma-388). |
| Ps | `47` | Salva il documento nel formato PS (PostScript). |
| Pcl | `48` | Salva il documento nel formato PCL (Printer Control Language). |
| Html | `50` | Salva il documento in formato HTML. |
| Mhtml | `51` | Salva il documento nel formato MHTML (Archivio Web). |
| Epub | `52` | Salva il documento nel formato EPUB. |
| Odt | `60` | Salva il documento come documento di testo ODF. |
| Ott | `61` | Salva il documento come modello di documento di testo ODF. |
| Text | `70` | Salva il documento nel formato di testo normale. |
| XamlFlow | `71` | **Beta.**Salva il documento nel formato Extensible Application Markup Language (XAML) come documento di flusso. |
| XamlFlowPack | `72` | **Beta.** Salva il documento nel formato del pacchetto Extensible Application Markup Language (XAML) come documento di flusso. |
| Markdown | `73` | Salva il documento nel formato Markdown. |
| Tiff | `100` | Visualizza una o più pagine del documento e le salva in un file TIFF a pagina singola o multipagina. |
| Png | `101` | Visualizza una pagina del documento e la salva come file PNG. |
| Bmp | `102` | Visualizza una pagina del documento e la salva come file BMP. |
| Emf | `103` | Visualizza una pagina del documento e la salva come file EMF (Enhanced Meta File) vettoriale. |
| Jpeg | `104` | Visualizza una pagina del documento e la salva come file JPEG. |
| Gif | `105` | Visualizza una pagina del documento e la salva come file GIF. |

### Esempi

Mostra come convertire da DOCX in formato HTML.

```csharp
Document doc = new Document(MyDir + "Document.docx");

doc.Save(ArtifactsDir + "Document.ConvertToHtml.html", SaveFormat.Html);
```

### Guarda anche

* method [Save](../document/save/)
* class [SaveOptions](../../aspose.words.saving/saveoptions/)
* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


