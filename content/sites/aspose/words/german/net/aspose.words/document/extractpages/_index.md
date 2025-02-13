---
title: Document.ExtractPages
second_title: Aspose.Words für .NET-API-Referenz
description: Document methode. Gibt die zurückDocument Objekt das einen bestimmten Seitenbereich darstellt.
type: docs
weight: 580
url: /de/net/aspose.words/document/extractpages/
---
## Document.ExtractPages method

Gibt die zurück[`Document`](../) Objekt, das einen bestimmten Seitenbereich darstellt.

```csharp
public Document ExtractPages(int index, int count)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| index | Int32 | Der nullbasierte Index der ersten zu extrahierenden Seite. |
| count | Int32 | Anzahl der zu extrahierenden Seiten. |

### Bemerkungen

Das resultierende Dokument sollte wie das in MS Word aussehen, als ob wir 'Bestimmte Seiten drucken' ausgeführt hätten – die Nummerierung, Kopf-/Fußzeilen und das Kreuztabellen-Layout bleiben erhalten. Aber aufgrund einer großen Anzahl von Nuancen, die erscheinen Während die Anzahl der Seiten reduziert wird, ist die vollständige Übereinstimmung des Layouts eine recht komplizierte Aufgabe, die viel Aufwand erfordert. Abhängig von der Komplexität des Dokuments kann es zu geringfügigen Unterschieden im resultierenden Layout des Dokumentinhalts im Vergleich zum Quelldokument kommen. Jegliches Feedback würde sehr geschätzt werden.

### Beispiele

Zeigt, wie der angegebene Seitenbereich aus dem Dokument abgerufen wird.

```csharp
Document doc = new Document(MyDir + "Layout entities.docx");

doc = doc.ExtractPages(0, 2);

doc.Save(ArtifactsDir + "Document.ExtractPages.docx");
```

### Siehe auch

* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


