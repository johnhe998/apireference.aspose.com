---
title: Interface IStructuredDocumentTag
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Markup.IStructuredDocumentTag interfaccia. Interfaccia per definire un dato comune perStructuredDocumentTag eStructuredDocumentTagRangeStart .
type: docs
weight: 3730
url: /it/net/aspose.words.markup/istructureddocumenttag/
---
## IStructuredDocumentTag interface

Interfaccia per definire un dato comune per[`StructuredDocumentTag`](../structureddocumenttag/) e[`StructuredDocumentTagRangeStart`](../structureddocumenttagrangestart/) .

```csharp
public interface IStructuredDocumentTag
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Color](../../aspose.words.markup/istructureddocumenttag/color/) { get; set; } | Ottiene o imposta il colore del tag del documento strutturato. |
| [Id](../../aspose.words.markup/istructureddocumenttag/id/) { get; } | Specifica un ID numerico persistente di sola lettura univoco per questo **SDT**. |
| [IsShowingPlaceholderText](../../aspose.words.markup/istructureddocumenttag/isshowingplaceholdertext/) { get; set; } | Specifica se il contenuto di questo **SDT** deve essere interpretato per contenere testo segnaposto (al contrario dei normali contenuti di testo all'interno dell'SDT). |
| [Level](../../aspose.words.markup/istructureddocumenttag/level/) { get; } | Ottiene il livello a cui questo **SDT** si verifica nell'albero dei documenti. |
| [LockContentControl](../../aspose.words.markup/istructureddocumenttag/lockcontentcontrol/) { get; set; } | Se impostata su true, questa proprietà vieterà a un utente di eliminarlo **SDT** . |
| [LockContents](../../aspose.words.markup/istructureddocumenttag/lockcontents/) { get; set; } | Se impostata su true, questa proprietà vieterà a un utente di modificarne il contenuto **SDT** . |
| [Placeholder](../../aspose.words.markup/istructureddocumenttag/placeholder/) { get; } | Ottiene il[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) contenente testo segnaposto che dovrebbe essere visualizzato quando il contenuto di questa esecuzione SDT è vuoto, l'elemento XML mappato associato è vuoto come specificato tramite[`XmlMapping`](./xmlmapping/) element o il[`IsShowingPlaceholderText`](./isshowingplaceholdertext/) elemento è vero. |
| [PlaceholderName](../../aspose.words.markup/istructureddocumenttag/placeholdername/) { get; set; } | Ottiene o imposta il nome del[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) contenente testo segnaposto. |
| [SdtType](../../aspose.words.markup/istructureddocumenttag/sdttype/) { get; } | Ottiene il tipo di questo **Tag del documento strutturato** . |
| [Tag](../../aspose.words.markup/istructureddocumenttag/tag/) { get; set; } | Specifica un tag associato al nodo SDT corrente. Non può essere null. |
| [Title](../../aspose.words.markup/istructureddocumenttag/title/) { get; set; } | Specifica il nome descrittivo associato a questo **SDT** . Non può essere nullo. |
| [WordOpenXML](../../aspose.words.markup/istructureddocumenttag/wordopenxml/) { get; } | Ottiene una stringa che rappresenta l'XML contenuto all'interno del nodo nel fileFlatOpc formato. |
| [XmlMapping](../../aspose.words.markup/istructureddocumenttag/xmlmapping/) { get; } | Ottiene un oggetto che rappresenta il mapping di questo tag del documento strutturato ai dati XML in una parte XML personalizzata del documento corrente. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [IsRanged](../../aspose.words.markup/istructureddocumenttag/isranged/)() | Restituisce true se questa istanza è un tag di documento strutturato con intervalli. |
| [StructuredDocumentTagNode](../../aspose.words.markup/istructureddocumenttag/structureddocumenttagnode/)() | Restituisce l'oggetto Node che implementa questa interfaccia. |

### Guarda anche

* spazio dei nomi [Aspose.Words.Markup](../../aspose.words.markup/)
* assemblea [Aspose.Words](../../)


