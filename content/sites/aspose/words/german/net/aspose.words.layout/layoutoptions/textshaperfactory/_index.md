---
title: LayoutOptions.TextShaperFactory
second_title: Aspose.Words für .NET-API-Referenz
description: LayoutOptions eigendom. Holt oder setztITextShaperFactory Implementierung die für erweiterte TypografieRenderingFunktionen verwendet wird.
type: docs
weight: 90
url: /de/net/aspose.words.layout/layoutoptions/textshaperfactory/
---
## LayoutOptions.TextShaperFactory property

Holt oder setzt[`ITextShaperFactory`](../../../aspose.words.shaping/itextshaperfactory/) Implementierung, die für erweiterte Typografie-Rendering-Funktionen verwendet wird.

```csharp
public ITextShaperFactory TextShaperFactory { get; set; }
```

### Beispiele

Zeigt, wie OpenType-Features mit der Textformungs-Engine HarfBuzz unterstützt werden.

```csharp
Document doc = new Document(MyDir + "OpenType text shaping.docx");

// Aspose.Words kann extern bereitgestellte Textformer-Objekte verwenden,
// die Schriftarten darstellen und Forminformationen für Text berechnen.
// Für Dokumente, die mehrere Schriftarten verwenden, ist eine Textformer-Factory erforderlich.
// Wenn der Textformer werkseitig eingestellt ist, verwendet das Layout OpenType-Funktionen.
// Eine Instance-Eigenschaft gibt ein statisches BasicTextShaperCache-Objekt zurück, das HarfBuzzTextShaperFactory umschließt.
doc.LayoutOptions.TextShaperFactory = HarfBuzzTextShaperFactory.Instance;

// Derzeit wird die Textformung beim Export in das PDF- oder XPS-Format durchgeführt.
doc.Save(ArtifactsDir + "Document.OpenType.pdf");
```

### Siehe auch

* interface [ITextShaperFactory](../../../aspose.words.shaping/itextshaperfactory/)
* class [LayoutOptions](../)
* namensraum [Aspose.Words.Layout](../../layoutoptions/)
* Montage [Aspose.Words](../../../)


