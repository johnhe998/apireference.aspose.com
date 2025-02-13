---
title: Cifrar Docx con contraseña
linktitle: Cifrar Docx con contraseña
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a cifrar un archivo DOCX con una contraseña usando Aspose.Words para .NET. Tutorial completo para la seguridad de los documentos.
type: docs
weight: 10
url: /es/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
En este tutorial, exploraremos el código fuente de C# proporcionado para cifrar un archivo DOCX con una contraseña usando Aspose.Words para .NET. Esta característica le permite proteger su documento haciéndolo accesible solo con una contraseña específica.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: Cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo DOCX para cargar.

## Paso 3: Configuración de las opciones de copia de seguridad de OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

En este paso, configuramos las opciones de guardado de OOXML creando un nuevo`OoxmlSaveOptions` objeto. Especificamos la contraseña deseada para cifrar el documento configurando el`Password` propiedad a su contraseña personalizada.

## Paso 4: Cifrar el documento con contraseña

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 En este último paso, guardamos el documento usando el`Save` y pasando la ruta al archivo de salida con el`.docx` extensión, junto con las opciones de guardado especificadas.

Ahora puede ejecutar el código fuente para cifrar su documento DOCX con una contraseña. El archivo resultante se guardará en el directorio especificado con el nombre "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx". Asegúrese de mantener segura su contraseña, ya que la necesitará para abrir el documento cifrado.

### Ejemplo de código fuente para Cifrar Docx con contraseña usando Aspose.Words para .NET 

```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Conclusión

En este tutorial, exploramos la funcionalidad de cifrar un archivo DOCX con una contraseña usando Aspose.Words para .NET. Aprendimos cómo proteger nuestros documentos haciéndolos accesibles solo con una contraseña específica.

El cifrado de documentos es una medida de seguridad esencial para proteger la información confidencial. Gracias a Aspose.Words for .NET podemos añadir fácilmente esta funcionalidad a nuestras aplicaciones.

Siguiendo los pasos proporcionados, puede integrar el cifrado de contraseñas en sus proyectos Aspose.Words para .NET y garantizar la confidencialidad de sus documentos.

Siéntase libre de experimentar con otras funciones que ofrece Aspose.Words para .NET para enriquecer sus aplicaciones con funciones avanzadas de manipulación de documentos.
