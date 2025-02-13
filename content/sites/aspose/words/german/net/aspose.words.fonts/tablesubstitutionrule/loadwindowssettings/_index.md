---
title: TableSubstitutionRule.LoadWindowsSettings
second_title: Aspose.Words für .NET-API-Referenz
description: TableSubstitutionRule methode. Lädt vordefinierte Tabellenersetzungseinstellungen für die WindowsPlattform.
type: docs
weight: 60
url: /de/net/aspose.words.fonts/tablesubstitutionrule/loadwindowssettings/
---
## TableSubstitutionRule.LoadWindowsSettings method

Lädt vordefinierte Tabellenersetzungseinstellungen für die Windows-Plattform.

```csharp
public void LoadWindowsSettings()
```

### Beispiele

Zeigt, wie auf Schriftartersetzungstabellen für Windows und Linux zugegriffen wird.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Erstellen Sie eine neue Tabellenersetzungsregel und laden Sie die standardmäßige Schriftartenersetzungstabelle von Microsoft Windows.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// In Windows ist der Standardersatz für die Schriftart "Times New Roman CE" "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Wir können die Tabelle in Form eines XML-Dokuments speichern.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// Linux hat seine eigene Substitutionstabelle.
// Es gibt mehrere Ersatzschriftarten für "Times New Roman CE".
// Wenn der erste Ersatz "FreeSerif" ebenfalls nicht verfügbar ist,
// Diese Regel durchläuft die anderen im Array, bis sie eine verfügbare findet.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Speichern Sie die Linux-Ersetzungstabelle in Form eines XML-Dokuments mithilfe eines Streams.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### Siehe auch

* class [TableSubstitutionRule](../)
* namensraum [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* Montage [Aspose.Words](../../../)


