---
title: Font.NameFarEast
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Gibt einen ostasiatischen Schriftartnamen zurück oder legt ihn fest.
type: docs
weight: 260
url: /de/net/aspose.words/font/namefareast/
---
## Font.NameFarEast property

Gibt einen ostasiatischen Schriftartnamen zurück oder legt ihn fest.

```csharp
public string NameFarEast { get; set; }
```

### Beispiele

Zeigt, wie Text in einer fernöstlichen Sprache eingefügt und formatiert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Geben Sie Schriftarteinstellungen an, die der Document Builder auf jeden Text anwendet, den er einfügt.
builder.Font.Name = "Courier New";
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// Benennen Sie "FarEast"-Äquivalente für unsere Schriftart und unser Gebietsschema.
// Wenn der Builder asiatische Zeichen mit dieser Font-Konfiguration einfügt, wird jeder Lauf, der enthält
// Diese Zeichen zeigen sie mit der Schriftart/dem Gebietsschema "FarEast" anstelle der Standardeinstellung an.
// Dies könnte nützlich sein, wenn eine westliche Schriftart keine ideale Darstellung für asiatische Zeichen hat.
builder.Font.NameFarEast = "SimSun";
builder.Font.LocaleIdFarEast = new CultureInfo("zh-CN", false).LCID;

// Dieser Text wird in der Standardschrift/dem Standardgebietsschema angezeigt.
builder.Writeln("Hello world!");

// Da es sich um asiatische Zeichen handelt, wendet dieser Lauf unsere "FarEast"-Font/Gebietsschema-Äquivalente an.
builder.Writeln("你好世界");

doc.Save(ArtifactsDir + "Font.FarEast.docx");
```

### Siehe auch

* property [Name](../name/)
* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


