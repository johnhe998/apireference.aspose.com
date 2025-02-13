---
title: Especificar fuente predeterminada al renderizar
linktitle: Especificar fuente predeterminada al renderizar
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para especificar la fuente predeterminada al representar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/specify-default-font-when-rendering/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para especificar la fuente predeterminada al representar un documento con Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo especificar una fuente predeterminada para usar al renderizar sus documentos usando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento para renderizar
 A continuación, debe cargar el documento para renderizar utilizando el`Document` clase. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: Establecer fuente predeterminada
 Ahora puede especificar la fuente predeterminada que se usará al renderizar creando una instancia de la`FontSettings` clase y establecer el`DefaultFontName`propiedad de la`DefaultFontSubstitution` objetar a la`DefaultFontSubstitution` objeto`SubstitutionSettings` de`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Paso 4: Guarde el documento renderizado
 Finalmente, puede guardar el documento renderizado en un archivo usando el`Save()` metodo de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Ejemplo de código fuente para Especificar fuente predeterminada al renderizar usando Aspose.Words para .NET 

```csharp
//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Si la fuente predeterminada definida aquí no se puede encontrar durante el renderizado, entonces
// en su lugar, se usa la fuente más cercana en la máquina.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Conclusión
En este tutorial, aprendimos a especificar la fuente predeterminada al representar un documento con Aspose.Words para .NET. Al seguir esta guía paso a paso, puede configurar fácilmente una fuente predeterminada para usar al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para el procesamiento de textos con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar la representación de sus documentos según sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo puedo especificar una fuente predeterminada al convertir a PDF en Aspose.Words?

 R: Para especificar una fuente predeterminada al convertir a PDF en Aspose.Words, puede usar el`PdfOptions`clase y establecer el`DefaultFontName` propiedad al nombre de la fuente deseada.

#### P: ¿Qué sucede si la fuente predeterminada no está disponible al convertir a PDF?

R: Si la fuente predeterminada especificada no está disponible al convertir a PDF, Aspose.Words utilizará una fuente de reemplazo para mostrar el texto en el documento convertido. Esto puede causar una ligera diferencia en la apariencia de la fuente original.

#### P: ¿Puedo especificar una fuente predeterminada para otros formatos de salida, como DOCX o HTML?

R: Sí, puede especificar una fuente predeterminada para otros formatos de salida, como DOCX o HTML, utilizando las opciones de conversión adecuadas y configurando la propiedad correspondiente para cada formato.

#### P: ¿Cómo puedo verificar la fuente predeterminada especificada en Aspose.Words?

 R: Para verificar la fuente predeterminada especificada en Aspose.Words, puede usar el`DefaultFontName`propiedad de la`PdfOptions` class y recuperar el nombre de la fuente configurada.

#### P: ¿Es posible especificar una fuente predeterminada diferente para cada sección del documento?

R: Sí, es posible especificar una fuente predeterminada diferente para cada sección del documento utilizando opciones de formato específicas para cada sección. Sin embargo, esto requeriría una manipulación más avanzada del documento utilizando las funciones de Aspose.Words.