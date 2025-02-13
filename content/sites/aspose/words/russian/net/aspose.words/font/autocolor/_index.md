---
title: Font.AutoColor
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Возвращает текущий рассчитанный цвет текста черный или белый который будет использоваться для автоцвета. Если цвет не авто то возвращаетColor .
type: docs
weight: 20
url: /ru/net/aspose.words/font/autocolor/
---
## Font.AutoColor property

Возвращает текущий рассчитанный цвет текста (черный или белый), который будет использоваться для «автоцвета». Если цвет не «авто», то возвращает[`Color`](../color/) .

```csharp
public Color AutoColor { get; }
```

### Примечания

Когда текст имеет «автоматический цвет», фактический цвет текста вычисляется автоматически , чтобы его можно было прочитать на фоне цвета фона. Когда вы меняете цвет фона, цвет текста автоматически переключается на черный или белый в MS Word, чтобы обеспечить максимальную читаемость.

### Примеры

Показывает, как улучшить читаемость, автоматически выбирая цвет текста в зависимости от яркости его фона.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Если объект Font прогона не указывает цвет текста, он будет автоматически
// выберите черный или белый цвет в зависимости от цвета фона.
Assert.AreEqual(Color.Empty.ToArgb(), builder.Font.Color.ToArgb());

// Цвет текста по умолчанию — черный. Если цвет фона темный, черный текст будет плохо видно.
// Чтобы решить эту проблему, свойство AutoColor будет отображать этот текст белым цветом.
builder.Font.Shading.BackgroundPatternColor = Color.DarkBlue;

builder.Writeln("The text color automatically chosen for this run is white.");

Assert.AreEqual(Color.White.ToArgb(), doc.FirstSection.Body.Paragraphs[0].Runs[0].Font.AutoColor.ToArgb());

// Если мы изменим фон на светлый цвет, черный будет более
// подходящий цвет текста, чем белый, чтобы автоматический цвет отображал его черным.
builder.Font.Shading.BackgroundPatternColor = Color.LightBlue;

builder.Writeln("The text color automatically chosen for this run is black.");

Assert.AreEqual(Color.Black.ToArgb(), doc.FirstSection.Body.Paragraphs[1].Runs[0].Font.AutoColor.ToArgb());

doc.Save(ArtifactsDir + "Font.SetFontAutoColor.docx");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


