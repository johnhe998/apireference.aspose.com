---
title: Interface IStructuredDocumentTag
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Markup.IStructuredDocumentTag koppel. Schnittstelle zum Definieren gemeinsamer Daten fürStructuredDocumentTag undStructuredDocumentTagRangeStart .
type: docs
weight: 3730
url: /de/net/aspose.words.markup/istructureddocumenttag/
---
## IStructuredDocumentTag interface

Schnittstelle zum Definieren gemeinsamer Daten für[`StructuredDocumentTag`](../structureddocumenttag/) und[`StructuredDocumentTagRangeStart`](../structureddocumenttagrangestart/) .

```csharp
public interface IStructuredDocumentTag
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Color](../../aspose.words.markup/istructureddocumenttag/color/) { get; set; } | Ruft die Farbe des strukturierten Dokument-Tags ab oder legt sie fest. |
| [Id](../../aspose.words.markup/istructureddocumenttag/id/) { get; } | Gibt eine eindeutige, schreibgeschützte, persistente numerische ID dafür an **SDT**. |
| [IsShowingPlaceholderText](../../aspose.words.markup/istructureddocumenttag/isshowingplaceholdertext/) { get; set; } | Gibt an, ob der Inhalt dieser **SDT** soll so interpretiert werden, dass es Platzhaltertext enthält (im Gegensatz zu regulären Textinhalten innerhalb des SDT). |
| [Level](../../aspose.words.markup/istructureddocumenttag/level/) { get; } | Ruft die Ebene ab, bei der dies der Fall ist **SDT** kommt im Dokumentbaum vor. |
| [LockContentControl](../../aspose.words.markup/istructureddocumenttag/lockcontentcontrol/) { get; set; } | Wenn diese Eigenschaft auf „true“ gesetzt ist, verhindert sie, dass ein Benutzer dies löscht **SDT** . |
| [LockContents](../../aspose.words.markup/istructureddocumenttag/lockcontents/) { get; set; } | Wenn diese Eigenschaft auf „true“ gesetzt ist, verbietet es einem Benutzer, den Inhalt von this zu bearbeiten **SDT** . |
| [Placeholder](../../aspose.words.markup/istructureddocumenttag/placeholder/) { get; } | Ruft die ab[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) Platzhaltertext enthält, der angezeigt werden soll, wenn der Inhalt dieses SDT-Laufs leer ist, das zugeordnete zugeordnete XML-Element leer ist, wie über angegeben[`XmlMapping`](./xmlmapping/) element oder die[`IsShowingPlaceholderText`](./isshowingplaceholdertext/) Element ist wahr. |
| [PlaceholderName](../../aspose.words.markup/istructureddocumenttag/placeholdername/) { get; set; } | Ruft den Namen der ab oder legt ihn fest[`BuildingBlock`](../../aspose.words.buildingblocks/buildingblock/) mit Platzhaltertext. |
| [SdtType](../../aspose.words.markup/istructureddocumenttag/sdttype/) { get; } | Ruft diesen Typ ab **Strukturiertes Dokument-Tag** . |
| [Tag](../../aspose.words.markup/istructureddocumenttag/tag/) { get; set; } | Gibt ein Tag an, das dem aktuellen SDT-Knoten zugeordnet ist. Darf nicht null sein. |
| [Title](../../aspose.words.markup/istructureddocumenttag/title/) { get; set; } | Gibt den zugehörigen Anzeigenamen an **SDT** . Darf nicht null sein. |
| [WordOpenXML](../../aspose.words.markup/istructureddocumenttag/wordopenxml/) { get; } | Ruft eine Zeichenfolge ab, die das XML darstellt, das im Knoten in der enthalten istFlatOpc format. |
| [XmlMapping](../../aspose.words.markup/istructureddocumenttag/xmlmapping/) { get; } | Ruft ein Objekt ab, das die Zuordnung dieses strukturierten Dokument-Tags zu XML-Daten in einem benutzerdefinierten XML-Teil des aktuellen Dokuments darstellt. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [IsRanged](../../aspose.words.markup/istructureddocumenttag/isranged/)() | Gibt „true“ zurück, wenn diese Instanz ein Bereichs-Tag für strukturierte Dokumente ist. |
| [StructuredDocumentTagNode](../../aspose.words.markup/istructureddocumenttag/structureddocumenttagnode/)() | Gibt das Node-Objekt zurück, das diese Schnittstelle implementiert. |

### Siehe auch

* namensraum [Aspose.Words.Markup](../../aspose.words.markup/)
* Montage [Aspose.Words](../../)


