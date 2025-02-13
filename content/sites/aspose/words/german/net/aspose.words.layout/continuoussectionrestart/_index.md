---
title: Enum ContinuousSectionRestart
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Layout.ContinuousSectionRestart opsomming. Stellt unterschiedliche Verhaltensweisen dar wenn Seitenzahlen in einem fortlaufenden Abschnitt berechnet werden der die Seitennummerierung neu startet.
type: docs
weight: 3100
url: /de/net/aspose.words.layout/continuoussectionrestart/
---
## ContinuousSectionRestart enumeration

Stellt unterschiedliche Verhaltensweisen dar, wenn Seitenzahlen in einem fortlaufenden Abschnitt berechnet werden, der die Seitennummerierung neu startet.

```csharp
public enum ContinuousSectionRestart
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Always | `0` | Die Seitennummerierung wird unabhängig vom Inhaltsfluss immer neu gestartet. |
| FromNewPageOnly | `1` | Die Seitennummerierung beginnt nur dann neu, wenn vor dem Abschnitt auf der Seite, auf der der Abschnitt beginnt, kein anderer Inhalt vorhanden ist. |

### Beispiele

Zeigt, wie die Seitennummerierung in einem fortlaufenden Abschnitt gesteuert wird.

```csharp
Document doc = new Document(MyDir + "Continuous section page numbering.docx");

// Standardmäßig entspricht das Verhalten von Aspose.Words dem von Microsoft Word 2019.
// Wenn Sie das alte Aspose.Words-Verhalten benötigen, sich wiederholendes Microsoft Word 2016, verwenden Sie 'ContinuousSectionRestart.FromNewPageOnly'.
// Die Seitennummerierung beginnt nur dann neu, wenn vor dem Abschnitt auf der Seite, auf der der Abschnitt beginnt, kein anderer Inhalt vorhanden ist.
// Aus diesem Grund wird die Nummerierung ab der zweiten Seite auf 2 zurückgesetzt.
doc.LayoutOptions.ContinuousSectionPageNumberingRestart = ContinuousSectionRestart.FromNewPageOnly;
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Layout.RestartPageNumberingInContinuousSection.pdf");
```

### Siehe auch

* namensraum [Aspose.Words.Layout](../../aspose.words.layout/)
* Montage [Aspose.Words](../../)


