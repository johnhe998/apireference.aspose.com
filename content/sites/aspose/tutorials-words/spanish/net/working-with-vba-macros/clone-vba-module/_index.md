---
title: Clonar módulo Vba desde un documento de Word
linktitle: Clonar módulo Vba desde un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: En este tutorial, aprenda a clonar un módulo de VBA desde un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-vba-macros/clone-vba-module/
---

En este tutorial, le diremos cómo clonar un módulo VBA de un documento de Word con macros utilizando la biblioteca Aspose.Words para .NET. La clonación de un módulo de VBA le permite reutilizar o copiar el código de VBA de un documento de origen a otro documento. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto
- Un documento de Word que contiene un proyecto VBA con el módulo que desea clonar

## Paso 1: Definir el directorio de documentos
 Primero, debe establecer la ruta del directorio en la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento de origen
A continuación, cargaremos el documento fuente de Word, que contiene el proyecto VBA y el módulo que queremos clonar.

```csharp
// Cargue el documento de origen
Document doc = new Document(dataDir + "VBA project.docm");
```

## Paso 3: Cree un nuevo documento con el proyecto VBA y clone el módulo
Crearemos un nuevo documento con un proyecto de VBA vacío y clonaremos el módulo especificado del documento de origen.

```csharp
// Cree un nuevo documento con un proyecto de VBA vacío
Document destDoc = new Document { VbaProject = new VbaProject() };

// Clonar el módulo
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Paso 4: Guarde el documento de destino
Finalmente, guardaremos el documento de destino con el módulo VBA clonado en un archivo.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Ejemplo de código fuente para Clone Vba Module usando Aspose.Words para .NET 
```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Conclusión
En este tutorial, vimos cómo clonar un módulo VBA de un documento de Word con macros usando Aspose.Words para .NET. La clonación de módulos VBA le permite reutilizar fácilmente el código VBA de un documento fuente en otro documento. Siéntase libre de usar esta función para organizar y administrar sus macros en diferentes documentos.

### Preguntas frecuentes

#### P: ¿Qué es duplicar un módulo VBA?

R: Duplicar un módulo VBA consiste en copiar un módulo que contiene código VBA de un documento fuente de Word a otro documento. Esto le permite reutilizar el código VBA en diferentes contextos o compartirlo con otros documentos.

#### P: ¿Cuáles son los requisitos previos para clonar un módulo VBA de un documento de Word?

R: Antes de poder clonar un módulo VBA de un documento de Word, debe tener un conocimiento práctico del lenguaje de programación C#. También necesita instalar la biblioteca Aspose.Words para .NET en su proyecto. Además, necesita un documento de Word que contenga un proyecto VBA con el módulo que desea clonar.

#### P: ¿Cómo configurar el directorio de documentos en el código?

 R: En el código provisto, debe reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta adecuada al directorio donde se encuentra el documento de Word que contiene el proyecto de VBA.

#### P: ¿Cómo guardar el documento de destino con el módulo VBA clonado?

 R: Para guardar el documento de destino con el módulo VBA clonado, puede usar el`Save` metodo de la`Document` clase especificando la ruta de destino deseada y el nombre de archivo.