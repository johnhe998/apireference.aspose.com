---
title: ParagraphFormat.WidowControl
second_title: Referencia de API de Aspose.Words para .NET
description: ParagraphFormat propiedad. Verdadero si la primera y la última línea del párrafo deben permanecer en la misma página que el resto del párrafo.
type: docs
weight: 390
url: /es/net/aspose.words/paragraphformat/widowcontrol/
---
## ParagraphFormat.WidowControl property

Verdadero si la primera y la última línea del párrafo deben permanecer en la misma página que el resto del párrafo.

```csharp
public bool WidowControl { get; set; }
```

### Ejemplos

Muestra cómo habilitar el control de viudas/huérfanas para un párrafo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Cuando escribimos el texto que no cabe en una página, una línea puede pasar a la página siguiente.
// La única línea que termina en la página siguiente se llama "huérfana",
// y la línea anterior donde el huérfano se separó se llama "Viuda".
// Podemos corregir huérfanos y viudas reorganizando el texto según el tamaño de fuente, el espaciado o los márgenes de página.
// Si deseamos conservar las dimensiones de nuestro documento, podemos establecer este indicador en "verdadero"
  // para empujar a las viudas a la misma página que sus respectivos huérfanos.
// Dejar esta marca como "falsa" dejará pares viuda/huérfana en el texto.
// Cada párrafo tiene esta configuración accesible en Microsoft Word a través de Inicio -> Párrafo -> Configuración de párrafo
// (botón en la esquina inferior derecha de la pestaña "Párrafo") -> "Control de viudas/huérfanos".
builder.ParagraphFormat.WidowControl = widowControl; 

// Insertar texto que produzca un huérfano y una viuda.
builder.Font.Size = 68;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "ParagraphFormat.WidowControl.docx");
```

### Ver también

* class [ParagraphFormat](../)
* espacio de nombres [Aspose.Words](../../paragraphformat/)
* asamblea [Aspose.Words](../../../)


