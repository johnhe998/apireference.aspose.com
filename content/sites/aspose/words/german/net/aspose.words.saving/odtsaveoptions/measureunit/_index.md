---
title: OdtSaveOptions.MeasureUnit
second_title: Aspose.Words für .NET-API-Referenz
description: OdtSaveOptions eigendom. Ermöglicht die Angabe von Maßeinheiten die auf den Dokumentinhalt angewendet werden sollen. Der Standardwert istCentimeters
type: docs
weight: 30
url: /de/net/aspose.words.saving/odtsaveoptions/measureunit/
---
## OdtSaveOptions.MeasureUnit property

Ermöglicht die Angabe von Maßeinheiten, die auf den Dokumentinhalt angewendet werden sollen. Der Standardwert istCentimeters

```csharp
public OdtSaveMeasureUnit MeasureUnit { get; set; }
```

### Bemerkungen

Open Office verwendet Zentimeter, wenn Längen, Breiten und andere messbare Formatierungen und Inhaltseigenschaften in Dokumenten angegeben werden, während MS Office Zoll verwendet.

### Beispiele

Zeigt, wie verschiedene Maßeinheiten zum Definieren von Stilparametern eines gespeicherten ODT-Dokuments verwendet werden.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Wenn wir das Dokument in .odt exportieren, können wir ein OdtSaveOptions-Objekt verwenden, um zu ändern, wie wir das Dokument speichern.
// Wir können die Eigenschaft "MeasureUnit" auf "OdtSaveMeasureUnit.Centimeters" setzen
// zum Definieren von Inhalten wie Stilparametern unter Verwendung des metrischen Systems, das Open Office verwendet. 
// Wir können die Eigenschaft "MeasureUnit" auf "OdtSaveMeasureUnit.Inches" setzen
// zum Definieren von Inhalten wie Stilparametern unter Verwendung des imperialen Systems, das Microsoft Word verwendet.
OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = odtSaveMeasureUnit
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### Siehe auch

* enum [OdtSaveMeasureUnit](../../odtsavemeasureunit/)
* class [OdtSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../odtsaveoptions/)
* Montage [Aspose.Words](../../../)


