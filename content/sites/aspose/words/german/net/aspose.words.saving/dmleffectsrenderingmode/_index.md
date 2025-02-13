---
title: Enum DmlEffectsRenderingMode
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.DmlEffectsRenderingMode opsomming. Gibt an wie DrawingMLEffekte in feste Seitenformate gerendert werden.
type: docs
weight: 4650
url: /de/net/aspose.words.saving/dmleffectsrenderingmode/
---
## DmlEffectsRenderingMode enumeration

Gibt an, wie DrawingML-Effekte in feste Seitenformate gerendert werden.

```csharp
public enum DmlEffectsRenderingMode
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Simplified | `0` | Das Rendern von DrawingML-Effekten wurde vereinfacht. |
| None | `1` | Es werden keine DrawingML-Effekte gerendert. |
| Fine | `2` | DrawingML-Effekte werden im Feinmodus gerendert, der eine erweiterte Verarbeitung erfordert. In diesem Modus liefert das Rendern von Effekten bessere Ergebnisse, jedoch zu höheren Leistungseinbußen alsSimplified Modus. |

### Beispiele

Zeigt, wie die Renderqualität von DrawingML-Effekten in einem Dokument konfiguriert wird, während wir es als PDF speichern.

```csharp
Document doc = new Document(MyDir + "DrawingML shape effects.docx");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Legen Sie die Eigenschaft "DmlEffectsRenderingMode" auf "DmlEffectsRenderingMode.None" fest, um alle DrawingML-Effekte zu verwerfen.
// Setzen Sie die Eigenschaft "DmlEffectsRenderingMode" auf "DmlEffectsRenderingMode.Simplified"
// um eine vereinfachte Version von DrawingML-Effekten zu rendern.
// Legen Sie die Eigenschaft "DmlEffectsRenderingMode" auf "DmlEffectsRenderingMode.Fine" fest
// Rendern von DrawingML-Effekten mit größerer Genauigkeit und auch mit höheren Verarbeitungskosten.
options.DmlEffectsRenderingMode = effectsRenderingMode;

Assert.AreEqual(DmlRenderingMode.DrawingML, options.DmlRenderingMode);

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLEffects.pdf", options);
```

### Siehe auch

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


