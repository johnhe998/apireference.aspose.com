---
title: Font.Emboss
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Истинно если шрифт отформатирован как рельефный.
type: docs
weight: 100
url: /ru/net/aspose.words/font/emboss/
---
## Font.Emboss property

Истинно, если шрифт отформатирован как рельефный.

```csharp
public bool Emboss { get; set; }
```

### Примеры

Показывает, как применять эффекты гравировки/тиснения к тексту.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 36;
builder.Font.Color = Color.LightBlue;

// Ниже приведены два способа использования теней для применения к тексту 3D-эффекта.
// 1 - Выгравировать текст, чтобы он выглядел так, будто буквы вдавлены в страницу:
builder.Font.Engrave = true;

builder.Writeln("This text is engraved.");

// 2 - Рельефный текст, чтобы он выглядел так, как будто буквы выпрыгивают из страницы:
builder.Font.Engrave = false;
builder.Font.Emboss = true;

builder.Writeln("This text is embossed.");

doc.Save(ArtifactsDir + "Font.EngraveEmboss.docx");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


