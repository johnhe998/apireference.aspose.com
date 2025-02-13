---
title: Enum TextBoxWrapMode
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.TextBoxWrapMode enum. Specifica come il testo va a capo allinterno di una forma.
type: docs
weight: 1190
url: /it/net/aspose.words.drawing/textboxwrapmode/
---
## TextBoxWrapMode enumeration

Specifica come il testo va a capo all'interno di una forma.

```csharp
public enum TextBoxWrapMode
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Square | `0` | Il testo va a capo all'interno di una forma. |
| None | `2` | Il testo non va a capo all'interno di una forma. |

### Esempi

Mostra come impostare una modalità di ritorno a capo per il contenuto di una casella di testo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 300, 300);
TextBox textBox = textBoxShape.TextBox;

// Imposta la proprietà "TextBoxWrapMode" su "TextBoxWrapMode.None" per aumentare la larghezza della casella di testo
// per contenere il testo, se è abbastanza grande.
// Imposta la proprietà "TextBoxWrapMode" su "TextBoxWrapMode.Square" su
// avvolge tutto il testo all'interno della casella di testo, preservandone le dimensioni.
textBox.TextBoxWrapMode = textBoxWrapMode;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Font.Size = 32;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "Shape.TextBoxContentsWrapMode.docx");
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Drawing](../../aspose.words.drawing/)
* assemblea [Aspose.Words](../../)


