---
title: Crear nueva línea de firma y establecer la identificación del proveedor
linktitle: Crear nueva línea de firma y establecer la identificación del proveedor
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a crear una nueva línea de firma y establecer la ID del proveedor en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
En este tutorial, lo guiaremos a través de los pasos para usar la función Crear nueva línea de firma y Establecer ID de proveedor con Aspose.Words para .NET. Esta función le permite insertar una línea de firma en un documento de Word, establecer opciones personalizadas y firmar el documento. Siga los pasos a continuación:

## Paso 1: Crear el Documento y el Generador

Comience creando una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Configuración de las opciones de la línea de firma

Cree una instancia de la clase SignatureLineOptions y establezca las opciones deseadas:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Paso 3: Inserción de la línea de firma

Utilice el método InsertSignatureLine() del objeto DocumentBuilder para insertar la línea de firma en el documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Paso 4: Establecer ID de proveedor

Establezca la ID del proveedor para la línea de firma usando la propiedad ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Asegúrese de especificar el ID de proveedor correcto para su caso de uso.

## Paso 5: Guarde el documento

Guarde el documento modificado:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento.

## Paso 6: Firma del documento

Para firmar el documento, debe configurar las opciones de firma y usar la clase DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Asegúrese de especificar las rutas correctas para el documento, el certificado y el documento firmado.

### Código fuente de ejemplo para crear una nueva línea de firma y establecer la identificación del proveedor usando Aspose.Words para .NET

Aquí está el código fuente completo para crear una nueva línea de firma y establecer la ID del proveedor con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Siguiendo estos pasos, puede crear fácilmente una nueva línea de firma y establecer la ID del proveedor en su documento de Word con Aspose.Words para .NET.

## Conclusión

En este tutorial, exploramos la característica de crear una nueva línea de firma y establecer la ID del proveedor en un documento de Word usando Aspose.Words para .NET. Siguiendo los pasos provistos, puede insertar fácilmente una línea de firma con opciones personalizadas y asociarla con un proveedor específico usando la ID del proveedor. Agregar líneas de firma y personalizar la información del proveedor mejora la autenticidad y confiabilidad de sus documentos. Aspose.Words for .NET proporciona una potente API para el procesamiento de textos con líneas de firma y certificados digitales en documentos de Word, lo que le permite automatizar el proceso de firma y garantizar la validez de sus documentos.

### Preguntas frecuentes

#### P: ¿Qué es una identificación de proveedor en una línea de firma?

R: Una ID de proveedor en una línea de firma es un identificador único que representa al proveedor de la firma digital. Ayuda a identificar la fuente u organización responsable de la firma.

#### P: ¿Cómo puedo crear una nueva línea de firma en un documento de Word usando Aspose.Words para .NET?

R: Para crear una nueva línea de firma en un documento de Word usando Aspose.Words para .NET, puede seguir estos pasos:
1.  Crear una instancia de la`Document` clase y un`DocumentBuilder` objeto.
2.  Crear una instancia de la`SignatureLineOptions` clase y establezca las opciones de línea de firma deseadas.
3.  Utilizar el`InsertSignatureLine` metodo de la`DocumentBuilder` objeto para insertar la línea de firma en el documento.

#### P: ¿Puedo personalizar las opciones de la línea de firma, como el nombre del firmante, el cargo y las instrucciones?

 R: Sí, puede personalizar las opciones de la línea de firma. El`SignatureLineOptions` class proporciona propiedades para establecer las opciones deseadas, como`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, etc. Puede modificar estas propiedades antes de insertar la línea de firma.

#### P: ¿Cuál es el propósito de configurar la ID del proveedor para una línea de firma?

R: Establecer la ID del proveedor para una línea de firma ayuda a identificar la fuente u organización responsable de la firma digital. Permite asociar la firma a un proveedor o entidad en concreto, aportando información adicional sobre el origen y fiabilidad de la firma.

#### P: ¿Cómo puedo configurar la ID del proveedor para una línea de firma usando Aspose.Words para .NET?

R: Para configurar la ID del proveedor para una línea de firma usando Aspose.Words para .NET, puede seguir estos pasos:
1.  Después de insertar la línea de firma, acceda a la`ProviderId`propiedad de la`SignatureLine` objeto.
2.  Selecciona el`ProviderId` propiedad al valor de ID de proveedor deseado usando el`Guid` tipo de datos.

#### P: ¿Puedo firmar el documento después de crear una nueva línea de firma y configurar la identificación del proveedor?

 R: Sí, después de crear una nueva línea de firma y configurar la identificación del proveedor, puede firmar el documento. Para firmar el documento, debe configurar las opciones de firma, incluida la identificación de la línea de firma, la identificación del proveedor, los comentarios y la hora de firma. Luego, usa el`DigitalSignatureUtil.Sign` método para firmar el documento mediante un certificado digital.

#### P: ¿Puedo especificar un ID de proveedor específico para cada línea de firma en un documento de Word?

R: Sí, puede especificar una identificación de proveedor específica para cada línea de firma en un documento de Word. Después de insertar cada línea de firma, puede establecer la ID del proveedor para esa línea de firma en particular accediendo a la`ProviderId` propiedad de los respectivos`SignatureLine` objeto.

#### P: ¿Cómo puedo guardar el documento modificado después de crear una nueva línea de firma y configurar la ID del proveedor?

 R: Para guardar el documento modificado después de crear una nueva línea de firma y configurar la ID del proveedor, puede usar el`Save` metodo de la`Document` objeto. Especifique la ruta y el nombre de archivo correctos para guardar el documento.

#### P: ¿Qué formato de archivo admite Aspose.Words para .NET para crear y firmar líneas de firma?

R: Aspose.Words para .NET admite la creación y firma de líneas de firma en el formato de archivo DOCX. Puede crear y firmar líneas de firma en archivos DOCX utilizando los métodos y clases proporcionados.

#### P: ¿Puedo modificar la identificación del proveedor u otras opciones de una línea de firma después de haberla firmado?

R: Una vez que se ha firmado una línea de firma, se convierte en parte del contenido del documento y no se puede modificar por separado. Cualquier modificación a la línea de firma, como cambiar la identificación del proveedor u otras opciones, requerirá eliminar la firma existente y crear una nueva línea de firma.