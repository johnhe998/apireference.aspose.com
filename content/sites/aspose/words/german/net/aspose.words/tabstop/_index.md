---
title: Class TabStop
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.TabStop klas. Repräsentiert einen einzelnen benutzerdefinierten Tabstopp. Das Tabulator Objekt ist Mitglied von the TabStopCollection Sammlung.
type: docs
weight: 5900
url: /de/net/aspose.words/tabstop/
---
## TabStop class

Repräsentiert einen einzelnen benutzerdefinierten Tabstopp. Das **Tabulator** Objekt ist Mitglied von the [`TabStopCollection`](../tabstopcollection/) Sammlung.

```csharp
public sealed class TabStop
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [TabStop](tabstop/#constructor)(double) | Initialisiert eine neue Instanz dieser Klasse. |
| [TabStop](tabstop/#constructor_1)(double, TabAlignment, TabLeader) | Initialisiert eine neue Instanz dieser Klasse. |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Alignment](../../aspose.words/tabstop/alignment/) { get; set; } | Ruft die Textausrichtung an diesem Tabstopp ab oder legt sie fest. |
| [IsClear](../../aspose.words/tabstop/isclear/) { get; } | Gibt „true“ zurück, wenn dieser Tabstopp alle vorhandenen Tabstopps an dieser Position löscht. |
| [Leader](../../aspose.words/tabstop/leader/) { get; set; } | Ermittelt oder setzt den Typ der Führungslinie, die unter dem Tabulatorzeichen angezeigt wird. |
| [Position](../../aspose.words/tabstop/position/) { get; } | Ruft die Position des Tabstopps in Punkten ab. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Equals](../../aspose.words/tabstop/equals/#equals)(TabStop) | Vergleicht mit dem angegebenen TabStop. |
| override [GetHashCode](../../aspose.words/tabstop/gethashcode/)() | Berechnet Hashcode für dieses Objekt. |

### Bemerkungen

Normalerweise gibt ein Tabstopp eine Position an, an der ein Tabstopp vorhanden ist. Da aber Tabstopps von übergeordneten Stilen geerbt werden können, kann es erforderlich sein, dass das untergeordnete Objekt ausdrücklich definiert, dass an einer bestimmten Position kein Tabstopp vorhanden ist. Um einen geerbten Tabstopp an einer bestimmten Position zu löschen , erstellen Sie a **Tabulator** Objekt und set [`Alignment`](./alignment/) zu`TabAlignment.Clear`.

Weitere Informationen finden Sie unter[`TabStopCollection`](../tabstopcollection/).

### Beispiele

Zeigt, wie die Position des rechten Tabstopps in TOC-bezogenen Absätzen geändert wird.

```csharp
Document doc = new Document(MyDir + "Table of contents.docx");

// Durch alle Absätze mit TOC-ergebnisbasierten Stilen iterieren; dies ist ein beliebiger Stil zwischen TOC und TOC9.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // Holen Sie sich den ersten in diesem Absatz verwendeten Tabulator, dies sollte der Tabulator sein, der zum Ausrichten der Seitenzahlen verwendet wird.
        TabStop tab = para.ParagraphFormat.TabStops[0];

        // Ersetzen Sie den ersten Standard-Tabstopp durch einen benutzerdefinierten Tabstopp.
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }

doc.Save(ArtifactsDir + "Styles.ChangeTocsTabStops.docx");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


