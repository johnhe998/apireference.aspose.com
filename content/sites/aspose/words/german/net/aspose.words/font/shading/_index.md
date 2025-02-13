---
title: Font.Shading
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Gibt ein ShadingObjekt zurück das sich auf die Schattierungsformatierung für die Schriftart bezieht.
type: docs
weight: 320
url: /de/net/aspose.words/font/shading/
---
## Font.Shading property

Gibt ein Shading-Objekt zurück, das sich auf die Schattierungsformatierung für die Schriftart bezieht.

```csharp
public Shading Shading { get; }
```

### Beispiele

Zeigt, wie Schattierung auf Text angewendet wird, der von einem Document Builder erstellt wurde.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Color = Color.White;

// Eine Möglichkeit, den mit unserer weißen Schriftfarbe erstellten Text sichtbar zu machen
// soll einen Hintergrundschattierungseffekt anwenden.
Shading shading = builder.Font.Shading;
shading.Texture = TextureIndex.TextureDiagonalUp;
shading.BackgroundPatternColor = Color.OrangeRed;
shading.ForegroundPatternColor = Color.DarkBlue;

builder.Writeln("White text on an orange background with a two-tone texture.");

doc.Save(ArtifactsDir + "Font.Shading.docx");
```

### Siehe auch

* class [Shading](../../shading/)
* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


