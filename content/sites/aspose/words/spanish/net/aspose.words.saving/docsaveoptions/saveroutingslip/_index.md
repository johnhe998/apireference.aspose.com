---
title: DocSaveOptions.SaveRoutingSlip
second_title: Referencia de API de Aspose.Words para .NET
description: DocSaveOptions propiedad. cuandofalso  los datos de RoutingSlip no se guardan en el documento de salida. El valor predeterminado es verdadero .
type: docs
weight: 60
url: /es/net/aspose.words.saving/docsaveoptions/saveroutingslip/
---
## DocSaveOptions.SaveRoutingSlip property

cuando`falso` , los datos de RoutingSlip no se guardan en el documento de salida. El valor predeterminado es **verdadero** .

```csharp
public bool SaveRoutingSlip { get; set; }
```

### Ejemplos

Muestra cómo configurar las opciones de guardado para formatos de Microsoft Word más antiguos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Hello world!");

DocSaveOptions options = new DocSaveOptions(SaveFormat.Doc);

// Establecer una contraseña que protegerá la carga del documento por Microsoft Word o Aspose.Words.
// Tenga en cuenta que esto no cifra el contenido del documento de ninguna manera.
options.Password = "MyPassword";

// Si el documento contiene una hoja de enrutamiento, podemos conservarlo mientras se guarda configurando este indicador en verdadero.
options.SaveRoutingSlip = true;

doc.Save(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", options);

// Para poder cargar el documento,
// necesitaremos aplicar la contraseña que especificamos en el objeto DocSaveOptions en un objeto LoadOptions.
Assert.Throws<IncorrectPasswordException>(() => doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc"));

LoadOptions loadOptions = new LoadOptions("MyPassword");
doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", loadOptions);

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Ver también

* class [DocSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../docsaveoptions/)
* asamblea [Aspose.Words](../../../)


