---
title: OdtSaveOptions.Password
second_title: Referencia de API de Aspose.Words para .NET
description: OdtSaveOptions propiedad. Obtiene o establece una contraseña para cifrar el documento.
type: docs
weight: 40
url: /es/net/aspose.words.saving/odtsaveoptions/password/
---
## OdtSaveOptions.Password property

Obtiene o establece una contraseña para cifrar el documento.

```csharp
public string Password { get; set; }
```

### Observaciones

Para guardar el documento sin encriptar, esta propiedad debe ser una cadena nula o vacía.

### Ejemplos

Muestra cómo cifrar un documento ODT/OTT guardado con una contraseña y luego cargarlo usando Aspose.Words.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Cree un nuevo OdtSaveOptions y pase "SaveFormat.Odt",
// o "SaveFormat.Ott" como formato para guardar el documento. 
OdtSaveOptions saveOptions = new OdtSaveOptions(saveFormat);
saveOptions.Password = "@sposeEncrypted_1145";

string extensionString = FileFormatUtil.SaveFormatToExtension(saveFormat);

// Si abrimos este documento con un editor apropiado,
// nos pedirá la contraseña que especificamos en el objeto SaveOptions.
doc.Save(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString, saveOptions);

FileFormatInfo docInfo = FileFormatUtil.DetectFileFormat(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString);

Assert.IsTrue(docInfo.IsEncrypted);

// Si deseamos abrir o editar este documento nuevamente usando Aspose.Words,
// tendremos que proporcionar un objeto LoadOptions con la contraseña correcta al constructor de carga.
doc = new Document(ArtifactsDir + "OdtSaveOptions.Encrypt" + extensionString,
    new LoadOptions("@sposeEncrypted_1145"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Ver también

* class [OdtSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../odtsaveoptions/)
* asamblea [Aspose.Words](../../../)


