---
title: FontInfoCollection.EmbedTrueTypeFonts
second_title: Aspose.Words für .NET-API-Referenz
description: FontInfoCollection eigendom. Gibt an ob TrueTypeSchriftarten in ein Dokument eingebettet werden wenn es gespeichert wird. Der Standardwert für diese Eigenschaft ist FALSCH .
type: docs
weight: 30
url: /de/net/aspose.words.fonts/fontinfocollection/embedtruetypefonts/
---
## FontInfoCollection.EmbedTrueTypeFonts property

Gibt an, ob TrueType-Schriftarten in ein Dokument eingebettet werden, wenn es gespeichert wird. Der Standardwert für diese Eigenschaft ist **FALSCH** .

```csharp
public bool EmbedTrueTypeFonts { get; set; }
```

### Bemerkungen

Das Einbetten von TrueType-Schriftarten ermöglicht es anderen, das Dokument mit denselben Schriftarten anzuzeigen, mit denen es erstellt wurde, , kann jedoch die Dokumentgröße erheblich erhöhen.

Diese Option funktioniert nur für die Formate DOC, DOCX und RTF.

### Beispiele

Zeigt, wie ein Dokument mit eingebetteten TrueType-Schriftarten gespeichert wird.

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### Siehe auch

* class [FontInfoCollection](../)
* namensraum [Aspose.Words.Fonts](../../fontinfocollection/)
* Montage [Aspose.Words](../../../)


