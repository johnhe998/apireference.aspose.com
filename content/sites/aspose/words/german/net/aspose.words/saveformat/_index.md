---
title: Enum SaveFormat
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.SaveFormat opsomming. Gibt das Format an in dem das Dokument gespeichert wird.
type: docs
weight: 4580
url: /de/net/aspose.words/saveformat/
---
## SaveFormat enumeration

Gibt das Format an, in dem das Dokument gespeichert wird.

```csharp
public enum SaveFormat
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Unknown | `0` | Ungültiger Standardwert für Dateiformat. |
| Doc | `10` | Speichert das Dokument im Microsoft Word 97-2007-Dokumentformat. |
| Dot | `11` | Speichert das Dokument im Microsoft Word 97-2007-Vorlagenformat. |
| Docx | `20` | Speichert das Dokument als Office Open XML WordprocessingML-Dokument (makrofrei). |
| Docm | `21` | Speichert das Dokument als Office Open XML WordprocessingML-Dokument mit Makros. |
| Dotx | `22` | Speichert das Dokument als Office Open XML WordprocessingML-Vorlage (makrofrei). |
| Dotm | `23` | Speichert das Dokument als Office Open XML WordprocessingML Macro-Enabled Template. |
| FlatOpc | `24` | Speichert das Dokument als Office Open XML WordprocessingML, das in einer flachen XML-Datei statt in einem ZIP-Paket gespeichert ist. |
| FlatOpcMacroEnabled | `25` | Speichert das Dokument als Office Open XML WordprocessingML Macro-Enabled Document, das in einer flachen XML-Datei statt in einem ZIP-Paket gespeichert wird. |
| FlatOpcTemplate | `26` | Speichert das Dokument als Office Open XML WordprocessingML-Vorlage (ohne Makros), die in einer flachen XML-Datei statt in einem ZIP-Paket gespeichert ist. |
| FlatOpcTemplateMacroEnabled | `27` | Speichert das Dokument als Office Open XML WordprocessingML Macro-Enabled Template, das in einer flachen XML-Datei statt in einem ZIP-Paket gespeichert wird. |
| Rtf | `30` | Speichert das Dokument im RTF-Format. Alle Zeichen über 7 Bit werden als Hexadezimal- oder Unicode-Zeichen maskiert. |
| WordML | `31` | Speichert das Dokument im Format Microsoft Word 2003 WordprocessingML. |
| Pdf | `40` | Speichert das Dokument im PDF-Format (Adobe Portable Document). |
| Xps | `41` | Speichert das Dokument im XPS-Format (XML Paper Specification). |
| XamlFixed | `42` | Speichert das Dokument im XAML-Format (Extensible Application Markup Language) als festes Dokument. |
| Svg | `44` | Speichert das Dokument im SVG-Format (Scalable Vector Graphics). |
| HtmlFixed | `45` | Speichert das Dokument im HTML-Format mit absolut positionierten Elementen |
| OpenXps | `46` | Speichert das Dokument im OpenXPS (Ecma-388)-Format. |
| Ps | `47` | Speichert das Dokument im PS-Format (PostScript). |
| Pcl | `48` | Speichert das Dokument im PCL-Format (Printer Control Language). |
| Html | `50` | Speichert das Dokument im HTML-Format. |
| Mhtml | `51` | Speichert das Dokument im MHTML-Format (Webarchiv). |
| Epub | `52` | Speichert das Dokument im EPUB-Format. |
| Odt | `60` | Speichert das Dokument als ODF-Textdokument. |
| Ott | `61` | Speichert das Dokument als ODF-Textdokumentvorlage. |
| Text | `70` | Speichert das Dokument im Nur-Text-Format. |
| XamlFlow | `71` | **Beta.**Speichert das Dokument im XAML-Format (Extensible Application Markup Language) als Flussdokument. |
| XamlFlowPack | `72` | **Beta.** Speichert das Dokument im XAML-Paketformat (Extensible Application Markup Language) als Flow-Dokument. |
| Markdown | `73` | Speichert das Dokument im Markdown-Format. |
| Tiff | `100` | Rendert eine oder mehrere Seiten des Dokuments und speichert sie in einer ein- oder mehrseitigen TIFF-Datei. |
| Png | `101` | Rendert eine Seite des Dokuments und speichert sie als PNG-Datei. |
| Bmp | `102` | Rendert eine Seite des Dokuments und speichert sie als BMP-Datei. |
| Emf | `103` | Rendert eine Seite des Dokuments und speichert sie als Vektor-EMF-Datei (Enhanced Meta File). |
| Jpeg | `104` | Rendert eine Seite des Dokuments und speichert sie als JPEG-Datei. |
| Gif | `105` | Rendert eine Seite des Dokuments und speichert sie als GIF-Datei. |

### Beispiele

Zeigt, wie Sie vom DOCX- in das HTML-Format konvertieren.

```csharp
Document doc = new Document(MyDir + "Document.docx");

doc.Save(ArtifactsDir + "Document.ConvertToHtml.html", SaveFormat.Html);
```

### Siehe auch

* method [Save](../document/save/)
* class [SaveOptions](../../aspose.words.saving/saveoptions/)
* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


