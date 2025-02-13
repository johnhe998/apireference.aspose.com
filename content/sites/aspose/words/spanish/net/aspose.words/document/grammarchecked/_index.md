---
title: Document.GrammarChecked
second_title: Referencia de API de Aspose.Words para .NET
description: Document propiedad. Devoluciones verdadero si se ha comprobado la gramática del documento.
type: docs
weight: 180
url: /es/net/aspose.words/document/grammarchecked/
---
## Document.GrammarChecked property

Devoluciones **verdadero** si se ha comprobado la gramática del documento.

```csharp
public bool GrammarChecked { get; set; }
```

### Observaciones

Para volver a comprobar la gramática del documento, establezca esta propiedad en **falso** .

### Ejemplos

Muestra cómo configurar la verificación ortográfica o gramatical.

```csharp
Document doc = new Document();

// La cadena con errores ortográficos.
doc.FirstSection.Body.FirstParagraph.Runs.Add(new Run(doc, "The speeling in this documentz is all broked."));

  // La verificación de ortografía/gramática comienza si establecemos las propiedades en falso.
// Podemos ver todos los errores en Microsoft Word a través de Revisar -> ortografía y Gramática.
// Tenga en cuenta que Microsoft Word no inicia automáticamente la revisión gramatical/ortográfica para los formatos de documento DOC y RTF.
doc.SpellingChecked = checkSpellingGrammar;
doc.GrammarChecked = checkSpellingGrammar;

doc.Save(ArtifactsDir + "Document.SpellingOrGrammar.docx");
```

### Ver también

* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)


