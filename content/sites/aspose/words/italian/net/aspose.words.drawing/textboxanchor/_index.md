---
title: Enum TextBoxAnchor
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.TextBoxAnchor enum. Specifica i valori utilizzati per lallineamento verticale del testo della forma.
type: docs
weight: 1180
url: /it/net/aspose.words.drawing/textboxanchor/
---
## TextBoxAnchor enumeration

Specifica i valori utilizzati per l'allineamento verticale del testo della forma.

```csharp
public enum TextBoxAnchor
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Top | `0` | Il testo è allineato alla parte superiore della casella di testo. |
| Middle | `1` | Il testo è allineato al centro della casella di testo. |
| Bottom | `2` | Il testo è allineato alla parte inferiore della casella di testo. |
| TopCentered | `3` | Il testo è allineato in alto al centro della casella di testo. |
| MiddleCentered | `4` | Il testo è allineato al centro della casella di testo. |
| BottomCentered | `5` | Il testo è allineato in basso al centro della casella di testo. |
| TopBaseline | `6` | Il testo è allineato alla linea di base superiore della casella di testo. |
| BottomBaseline | `7` | Il testo è allineato alla linea di base inferiore della casella di testo. |
| TopCenteredBaseline | `8` | Il testo è allineato alla linea di base centrata in alto della casella di testo. |
| BottomCenteredBaseline | `9` | Il testo è allineato alla linea di base centrata in basso della casella di testo. |

### Esempi

Mostra come allineare verticalmente il contenuto del testo di una casella di testo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.TextBox, 200, 200);

// Imposta la proprietà "VerticalAnchor" su "TextBoxAnchor.Top" su
// allinea il testo in questa casella di testo con il lato superiore della forma.
// Imposta la proprietà "VerticalAnchor" su "TextBoxAnchor.Middle" su
// allinea il testo in questa casella di testo al centro della forma.
// Imposta la proprietà "VerticalAnchor" su "TextBoxAnchor.Bottom" su
// allinea il testo in questa casella di testo alla parte inferiore della forma.
shape.TextBox.VerticalAnchor = verticalAnchor;

builder.MoveTo(shape.FirstParagraph);
builder.Write("Hello world!");

// L'allineamento verticale del testo all'interno delle caselle di testo è disponibile da Microsoft Word 2007 in poi.
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2007);
doc.Save(ArtifactsDir + "Shape.VerticalAnchor.docx");
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Drawing](../../aspose.words.drawing/)
* assemblea [Aspose.Words](../../)


