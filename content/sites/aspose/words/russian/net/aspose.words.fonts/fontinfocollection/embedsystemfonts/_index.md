---
title: FontInfoCollection.EmbedSystemFonts
second_title: Справочник по API Aspose.Words для .NET
description: FontInfoCollection свойство. Указывает следует ли встраивать системные шрифты в документ. Значение по умолчанию для этого свойства ЛОЖЬ.
type: docs
weight: 20
url: /ru/net/aspose.words.fonts/fontinfocollection/embedsystemfonts/
---
## FontInfoCollection.EmbedSystemFonts property

Указывает, следует ли встраивать системные шрифты в документ. Значение по умолчанию для этого свойства: **ЛОЖЬ**.

Этот вариант работает только тогда, когда[`EmbedTrueTypeFonts`](../embedtruetypefonts/) опция установлена на **истинный**.

```csharp
public bool EmbedSystemFonts { get; set; }
```

### Примечания

Установка для этого свойства значения`Истинный`полезно, если пользователь работает в восточноазиатской системе system и хочет создать документ, который смогут прочитать другие пользователи, у которых в системе нет шрифтов для языка this . Например, пользователь японской системы может выбрать встраивание шрифтов the в документ, чтобы японский документ можно было прочитать на всех системах.

Эта опция работает только для форматов DOC, DOCX и RTF.

### Примеры

Показывает, как сохранить документ со встроенными шрифтами TrueType.

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

### Смотрите также

* class [FontInfoCollection](../)
* пространство имен [Aspose.Words.Fonts](../../fontinfocollection/)
* сборка [Aspose.Words](../../../)


