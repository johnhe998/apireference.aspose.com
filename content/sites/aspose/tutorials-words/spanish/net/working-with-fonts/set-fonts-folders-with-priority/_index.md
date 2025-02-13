---
title: Establecer carpetas de fuentes con prioridad
linktitle: Establecer carpetas de fuentes con prioridad
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para configurar carpetas de fuentes con prioridad al renderizar un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-with-priority/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para establecer carpetas de fuentes con prioridad al procesar un documento usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo especificar varias carpetas de fuentes con prioridad de búsqueda personalizada al representar sus documentos con Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Establecer carpetas de fuentes con prioridad
 Luego puede configurar las carpetas de fuentes con prioridad usando el`FontSettings` clase y el`SetFontsSources()`método. Puede especificar varias fuentes de fuentes utilizando instancias de`SystemFontSource` y`FolderFontSource`. En este ejemplo, hemos definido dos orígenes de fuentes: el origen de fuentes del sistema predeterminado y una carpeta de fuentes personalizada con una prioridad de 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Paso 3: Cargue el documento para renderizar
 Ahora puede cargar el documento para renderizar usando el`Document` clase. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 4: Guarde el documento renderizado
 Finalmente, puede guardar el documento renderizado en un archivo usando el`Save()` metodo de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Ejemplo de código fuente para Establecer carpetas de fuentes con prioridad usando Aspose.Words para .NET 
```csharp
//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo establecer carpetas de fuentes con prioridad al renderizar un documento usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede especificar fácilmente varias carpetas de fuentes con prioridad de búsqueda personalizada al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para el procesamiento de textos con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar las fuentes de fuentes utilizadas al renderizar sus documentos según sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo puedo establecer carpetas de fuentes con prioridad en Aspose.Words?

 R: Para establecer carpetas de fuentes con prioridad en Aspose.Words, puede usar el`SetFontsFoldersWithPriority` metodo de la`Fonts` class especificando las ubicaciones de las carpetas de fuentes y su orden de prioridad.

#### P: ¿Qué sucede si una fuente está presente en varias carpetas con diferente prioridad?

R: Si una fuente está presente en varias carpetas con diferente prioridad, Aspose.Words utilizará la versión de la carpeta con la prioridad más alta al procesar documentos.

#### P: ¿Puedo especificar varias carpetas de fuentes con la misma prioridad en Aspose.Words?

R: Sí, puede especificar varias carpetas de fuentes con la misma prioridad en Aspose.Words. Aspose.Words los considerará a todos con igual prioridad al buscar fuentes en sus documentos.

#### P: ¿Cómo puedo verificar las carpetas de fuentes definidas con prioridad en Aspose.Words?

 R: Para verificar las carpetas de fuentes definidas con prioridad en Aspose.Words, puede usar el`GetFolders` metodo de la`Fonts` class para obtener la lista de carpetas de fuentes configuradas, incluido su orden de prioridad.

#### P: ¿De qué sirve configurar carpetas de fuentes con prioridad en Aspose.Words?

R: Establecer carpetas de fuentes con prioridad en Aspose.Words le permite controlar el orden de búsqueda de las fuentes en sus documentos de Word. Esto le ayuda a asegurarse de que se utilizan las fuentes que desea y a evitar problemas de sustitución de fuentes no deseadas.