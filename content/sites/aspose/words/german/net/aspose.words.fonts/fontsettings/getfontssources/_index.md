---
title: FontSettings.GetFontsSources
second_title: Aspose.Words für .NET-API-Referenz
description: FontSettings methode. Ruft eine Kopie des Arrays ab das die Liste der Quellen enthält in denen Aspose.Words nach TrueTypeSchriftarten sucht.
type: docs
weight: 50
url: /de/net/aspose.words.fonts/fontsettings/getfontssources/
---
## FontSettings.GetFontsSources method

Ruft eine Kopie des Arrays ab, das die Liste der Quellen enthält, in denen Aspose.Words nach TrueType-Schriftarten sucht.

```csharp
public FontSourceBase[] GetFontsSources()
```

### Rückgabewert

Eine Kopie der aktuellen Schriftartquellen.

### Bemerkungen

Der zurückgegebene Wert ist eine Kopie der Daten, die Aspose.Words verwendet. Wenn Sie die entries im zurückgegebenen Array ändern, hat dies keine Auswirkung auf das Rendern des Dokuments. Um neue Schriftarten festzulegen, verwenden Sie sources [`SetFontsSources`](../setfontssources/) Methode.

### Beispiele

Zeigt, wie eine Schriftartquelle zu unseren vorhandenen Schriftartquellen hinzugefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");
builder.Font.Name = "Junction Light";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, originalFontSources.Length);

Assert.True(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// Der Standard-Schriftquelle fehlen zwei der Schriftarten, die wir in unserem Dokument verwenden.
// Wenn wir dieses Dokument speichern, wendet Aspose.Words Fallback-Schriftarten auf allen Text an, der mit nicht zugänglichen Schriftarten formatiert ist.
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));

// Erstellen Sie eine Schriftartquelle aus einem Ordner, der Schriftarten enthält.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);

// Wenden Sie ein neues Array von Schriftartquellen an, das die ursprünglichen Schriftartquellen sowie unsere benutzerdefinierten Schriftarten enthält.
FontSourceBase[] updatedFontSources = {originalFontSources[0], folderFontSource};
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);

// Stellen Sie sicher, dass Aspose.Words Zugriff auf alle erforderlichen Schriftarten hat, bevor wir das Dokument als PDF rendern.
updatedFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.True(updatedFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(updatedFontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
Assert.True(updatedFontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));

doc.Save(ArtifactsDir + "FontSettings.AddFontSource.pdf");

// Stellen Sie die ursprünglichen Schriftartquellen wieder her.
FontSettings.DefaultInstance.SetFontsSources(originalFontSources);
```

### Siehe auch

* class [FontSourceBase](../../fontsourcebase/)
* class [FontSettings](../)
* namensraum [Aspose.Words.Fonts](../../fontsettings/)
* Montage [Aspose.Words](../../../)


