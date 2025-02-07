---
title: Document.UpdatePageLayout
second_title: Aspose.Words für .NET-API-Referenz
description: Document methode. Baut das Seitenlayout des Dokuments neu auf.
type: docs
weight: 750
url: /de/net/aspose.words/document/updatepagelayout/
---
## Document.UpdatePageLayout method

Baut das Seitenlayout des Dokuments neu auf.

```csharp
public void UpdatePageLayout()
```

### Bemerkungen

Diese Methode formatiert ein Dokument in Seiten und aktualisiert die Seitenzahl-bezogenen Felder im Dokument wie wie PAGE, PAGES, PAGEREF und REF. Die aktuellen Seitenlayoutinformationen werden für eine korrekte Wiedergabe des Dokuments in feste Seitenformate benötigt.

Diese Methode wird automatisch aufgerufen, wenn Sie ein Dokument zum ersten Mal in PDF, XPS, Bild konvertieren oder drucken. Wenn Sie das Dokument jedoch nach dem Rendern ändern und dann erneut versuchen, es zu rendern, aktualisiert Aspose.Words das Seitenlayout nicht automatisch. In diesem Fall sollten Sie anrufen`UpdatePageLayout` before Rendern erneut.

### Beispiele

Zeigt an, wann das Seitenlayout des Dokuments neu berechnet werden soll.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Das Speichern eines Dokuments als PDF, in ein Bild oder das erstmalige Drucken erfolgt automatisch
// das Layout des Dokuments innerhalb seiner Seiten zwischenspeichern.
doc.Save(ArtifactsDir + "Document.UpdatePageLayout.1.pdf");

// Ändern Sie das Dokument auf irgendeine Weise.
doc.Styles["Normal"].Font.Size = 6;
doc.Sections[0].PageSetup.Orientation = Aspose.Words.Orientation.Landscape;

 // In der aktuellen Version von Aspose.Words wird das Dokument nicht automatisch neu erstellt, wenn es geändert wird
// das zwischengespeicherte Seitenlayout. Wenn wir das zwischengespeicherte Layout wünschen
// Um auf dem neuesten Stand zu bleiben, müssen wir es manuell aktualisieren.
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Document.UpdatePageLayout.2.pdf");
```

### Siehe auch

* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


