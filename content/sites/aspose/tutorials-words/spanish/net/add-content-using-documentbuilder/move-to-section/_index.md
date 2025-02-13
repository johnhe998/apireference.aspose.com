---
title: Mover a la sección
linktitle: Mover a la sección
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para usar Mover a la sección en Aspose.Words para .NET manipular secciones y párrafos en documentos de Word.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/move-to-section/
---

En este ejemplo, le explicaremos cómo utilizar la función Mover a la sección de Aspose.Words para .NET paso a paso utilizando el código fuente de C# proporcionado. Esta característica le permite navegar y manipular diferentes secciones dentro de un documento de Word. Siga los pasos a continuación para integrar esta funcionalidad en su aplicación.

## Paso 1: Cree un nuevo documento y agregue una sección

Primero, necesitamos crear un nuevo documento y agregarle una sección. Utilice el siguiente código para realizar este paso:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Este código crea un nuevo documento vacío y agrega una sección a este documento.

## Paso 2: Mueva DocumentBuilder a la segunda sección y agregue texto

A continuación, debemos mover DocumentBuilder a la segunda sección del documento y agregar algo de texto allí. Use el siguiente código para realizar este paso:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Este código crea un DocumentBuilder a partir del documento existente, luego mueve el cursor del DocumentBuilder a la segunda sección del documento. Finalmente, agrega el texto especificado a esta sección.

## Paso 3: Cargue un documento con párrafos existentes

Si desea trabajar con un documento existente que contiene párrafos, puede cargar este documento utilizando el siguiente código:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Este código carga el documento especificado (reemplace "MyDir + "Paragraphs.docx""con la ruta real a su documento) y accede a la colección de párrafos de la primera sección del documento. La línea`Assert.AreEqual(22, paragraphs.Count);` comprueba que el documento contiene 22 párrafos.

## Paso 4: cree un DocumentBuilder para un documento

Puede crear el cursor de DocumentBuilder en un párrafo específico utilizando índices posicionales.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Paso 5: Mover el cursor al párrafo específico


Puede mover el cursor de DocumentBuilder a un párrafo específico usando índices posicionales. Aquí está cómo hacerlo:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Este código mueve el cursor del DocumentBuilder al tercer párrafo de la segunda sección (párrafo en el índice 2) y a la posición 10. Luego agrega un nuevo párrafo con algo de texto y verifica que el cursor esté bien posicionado en este nuevo párrafo.

### Ejemplo de código fuente para Mover a Mover a la sección usando Aspose.Words para .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Mueva un DocumentBuilder a la segunda sección y agregue texto.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Crear documento con párrafos.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

//Cuando creamos un DocumentBuilder para un documento, su cursor está al principio del documento de forma predeterminada,
// y cualquier contenido agregado por DocumentBuilder simplemente se agregará al documento.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// Puede mover el cursor a cualquier posición en un párrafo.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Eso es todo ! Ahora ha entendido cómo usar la funcionalidad de mover a la sección de Aspose.Words para .NET usando el código fuente proporcionado. Ahora puede integrar esta funcionalidad en su propia aplicación y manipular secciones y párrafos de sus documentos de Word de forma dinámica.

