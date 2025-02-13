---
title: Insertar campo
linktitle: Insertar campo
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar un campo en sus documentos de Word con Aspose.Words para .NET. Personaliza tus documentos con campos dinámicos.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-field/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la función "Insertar un campo" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear el Documento y DocumentBuilder

Comenzamos creando un nuevo documento e inicializando un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Insertar el campo

 usamos el`InsertField()` del DocumentBuilder para insertar un campo en el documento. En este ejemplo, insertamos un campo de combinación (MERGEFIELD) con el nombre de campo "MyFieldName" y formato de combinación.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Ejemplo del código fuente para insertar un campo con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento y el DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta el campo.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

En este ejemplo, creamos un nuevo documento, inicializamos un DocumentBuilder y luego insertamos un campo de combinación con el nombre de campo "MyFieldName" y el formato de combinación. A continuación, el documento se guarda con un nombre de archivo especificado.

Esto concluye nuestra guía sobre el uso de la función "Insertar un campo" con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Qué es un campo en Word?

R: Un campo en Word es un elemento que le permite insertar y manipular datos dinámicos en un documento. Se puede utilizar para mostrar información variable como fechas, números de página, tablas, fórmulas matemáticas, etc.

#### P: ¿Cómo insertar un campo en un documento de Word?

R: Para insertar un campo en un documento de Word, puede seguir estos pasos:

1. Coloque el cursor donde desee insertar el campo.
2. Vaya a la pestaña "Insertar" en la cinta.
3. Haga clic en el botón "Campo" en el grupo "Texto" para abrir el cuadro de diálogo de campos.
4. Seleccione el tipo de campo que desea insertar de la lista desplegable.
5. Configure las opciones de campo según sea necesario.
6. Haga clic en el botón "Aceptar" para insertar el campo en su documento.

#### P: ¿Cuáles son los tipos de campo de uso común en Word?

R: Word ofrece una amplia variedad de tipos de campos que puede usar en sus documentos. Estos son algunos de los tipos de campo más utilizados:

- Fecha y hora: muestra la fecha y la hora actuales.
- Número de página: muestra el número de página actual.
- Tabla de contenido: genera automáticamente una tabla de contenido basada en los estilos de sus títulos.
- Cálculo: realiza cálculos matemáticos mediante fórmulas.
- Texto de relleno: genera texto aleatorio para rellenar su documento.

#### P: ¿Puedo personalizar la apariencia de los campos en Word?

R: Sí, puede personalizar la apariencia de los campos en Word usando las opciones de formato disponibles. Por ejemplo, puede cambiar la fuente, el tamaño, el color y el estilo del texto en un campo. También puede aplicar efectos de formato como negrita, cursiva y subrayado.
  