---
title: LoadOptions.FontSettings
second_title: Aspose.Words für .NET-API-Referenz
description: LoadOptions eigendom. Ermöglicht das Festlegen von Schrifteinstellungen für Dokumente.
type: docs
weight: 70
url: /de/net/aspose.words.loading/loadoptions/fontsettings/
---
## LoadOptions.FontSettings property

Ermöglicht das Festlegen von Schrifteinstellungen für Dokumente.

```csharp
public FontSettings FontSettings { get; set; }
```

### Bemerkungen

Beim Laden einiger Formate muss Aspose.Words möglicherweise die Schriftarten auflösen. Wenn beispielsweise HTML-Dokumente geladen werden, kann Aspose.Words die Schriftarten auflösen, um eine Fallback-Funktion für Schriftarten auszuführen.

Wenn auf null gesetzt, werden standardmäßig statische Schriftarteinstellungen verwendet[`DefaultInstance`](../../../aspose.words.fonts/fontsettings/defaultinstance/) wird verwendet.

Der Standardwert ist null.

### Beispiele

Zeigt, wie Einstellungen für die Schriftartersetzung beim Laden eines Dokuments angewendet werden.

```csharp
// Erstellen Sie ein FontSettings-Objekt, das die Schriftart "Times New Roman" ersetzt
// mit der Schriftart „Arvo“ aus unserem Ordner „MyFonts“.
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(FontsDir, false);
fontSettings.SubstitutionSettings.TableSubstitution.AddSubstitutes("Times New Roman", "Arvo");

// Dieses FontSettings-Objekt als Eigenschaft eines neu erstellten LoadOptions-Objekts festlegen.
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;

// Laden Sie das Dokument und rendern Sie es dann als PDF mit der Schriftersetzung.
Document doc = new Document(MyDir + "Document.docx", loadOptions);

doc.Save(ArtifactsDir + "LoadOptions.FontSettings.pdf");
```

Zeigt, wie während des Ladens Schriftersetzungen festgelegt werden.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = new FontSettings();

// Festlegen einer Schriftersetzungsregel für ein LoadOptions-Objekt.
// Wenn das Dokument, das wir laden, eine Schriftart verwendet, die wir nicht haben,
// Diese Regel ersetzt die nicht verfügbare Schriftart durch eine vorhandene.
// In diesem Fall werden alle Verwendungen von „MissingFont“ in „Comic Sans MS“ konvertiert.
TableSubstitutionRule substitutionRule = loadOptions.FontSettings.SubstitutionSettings.TableSubstitution;
substitutionRule.AddSubstitutes("MissingFont", new[] {"Comic Sans MS"});

Document doc = new Document(MyDir + "Missing font.html", loadOptions);

// Zu diesem Zeitpunkt befindet sich dieser Text noch in "MissingFont".
// Die Schriftartersetzung findet statt, wenn wir das Dokument rendern.
Assert.AreEqual("MissingFont", doc.FirstSection.Body.FirstParagraph.Runs[0].Font.Name);

doc.Save(ArtifactsDir + "FontSettings.ResolveFontsBeforeLoadingDocument.pdf");
```

### Siehe auch

* class [FontSettings](../../../aspose.words.fonts/fontsettings/)
* class [LoadOptions](../)
* namensraum [Aspose.Words.Loading](../../loadoptions/)
* Montage [Aspose.Words](../../../)


