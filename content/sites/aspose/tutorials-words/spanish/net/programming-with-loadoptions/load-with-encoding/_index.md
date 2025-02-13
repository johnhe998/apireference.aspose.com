---
title: Cargar con codificación
linktitle: Cargar con codificación
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a cargar un documento con una codificación específica utilizando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-loadoptions/load-with-encoding/
---
Cuando se utiliza el procesamiento de textos con documentos de texto en una aplicación C#, es importante poder cargarlos correctamente especificando la codificación correcta. Con la biblioteca Aspose.Words para .NET, puede cargar fácilmente documentos de texto con la codificación deseada utilizando las opciones de carga de LoadOptions. En esta guía paso a paso, lo guiaremos a través de cómo usar Aspose.Words para el código fuente de .NET C# para cargar un documento de texto con la codificación especificada usando las opciones de carga de LoadOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Configuración de las opciones de carga

El primer paso es configurar las opciones de carga de nuestro documento de texto. Utilice la clase LoadOptions para especificar los parámetros de carga. En nuestro caso, debemos establecer la propiedad Codificación en la codificación deseada, por ejemplo, Codificación.UTF7 para la codificación UTF-7. Aquí está cómo hacerlo:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };
```

Creamos un nuevo objeto LoadOptions y establecemos la propiedad Encoding en Encoding.UTF7 para especificar la codificación UTF-7.

## Cargando documento con codificación especificada

Ahora que hemos configurado las opciones de carga, podemos cargar el documento usando la clase Document y especificar las opciones de carga. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

En este ejemplo, cargamos el documento "Codificado en UTF-7.txt" ubicado en el directorio de documentos utilizando las opciones de carga especificadas.

### Ejemplo de código fuente para LoadOptions con la funcionalidad "Cargar con codificación" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configurar las opciones de carga con la codificación deseada (UTF-7)
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };

// Cargue el documento con la codificación especificada
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

## Conclusión

En esta guía, explicamos cómo cargar un documento de texto con una codificación específica utilizando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. La carga de documentos de texto con la codificación adecuada garantiza una lectura correcta y precisa del contenido de su aplicación.