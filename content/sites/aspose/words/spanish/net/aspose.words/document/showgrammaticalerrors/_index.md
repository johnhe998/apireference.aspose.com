---
title: Document.ShowGrammaticalErrors
second_title: Referencia de API de Aspose.Words para .NET
description: Document propiedad. Especifica si mostrar errores gramaticales en este documento.
type: docs
weight: 370
url: /es/net/aspose.words/document/showgrammaticalerrors/
---
## Document.ShowGrammaticalErrors property

Especifica si mostrar errores gramaticales en este documento.

```csharp
public bool ShowGrammaticalErrors { get; set; }
```

### Ejemplos

Muestra cómo mostrar/ocultar errores en el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta dos oraciones con errores que serían recogidos
// por los correctores ortográficos y gramaticales en Microsoft Word.
builder.Writeln("There is a speling error in this sentence.");
builder.Writeln("Their is a grammatical error in this sentence.");

// Si estas opciones están habilitadas, los errores ortográficos aparecerán subrayados
// en el documento de salida por una línea roja irregular y una línea azul doble resaltará los errores gramaticales.
doc.ShowGrammaticalErrors = showErrors;
doc.ShowSpellingErrors = showErrors;

doc.Save(ArtifactsDir + "Document.SpellingAndGrammarErrors.docx");
```

### Ver también

* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)


