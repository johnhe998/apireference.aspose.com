---
title: Font.LocaleId
second_title: Referencia de API de Aspose.Words para .NET
description: Font propiedad. Obtiene o establece el identificador de configuración regional idioma de los caracteres con formato.
type: docs
weight: 200
url: /es/net/aspose.words/font/localeid/
---
## Font.LocaleId property

Obtiene o establece el identificador de configuración regional (idioma) de los caracteres con formato.

```csharp
public int LocaleId { get; set; }
```

### Observaciones

Para ver la lista de identificadores de configuración regional, consulte https://msdn.microsoft.com/en-us/library/cc233965.aspx

### Ejemplos

Muestra cómo establecer la configuración regional del texto que estamos agregando con un generador de documentos.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Si configuramos la configuración regional de la fuente en inglés e insertamos texto en ruso,
// el corrector ortográfico del idioma inglés no reconocerá el texto y lo detectará como un error ortográfico.
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;
builder.Writeln("Привет!");

// Establecer una configuración regional coincidente para el texto que estamos a punto de agregar para aplicar el corrector ortográfico apropiado.
builder.Font.LocaleId = new CultureInfo("ru-RU", false).LCID;
builder.Writeln("Привет!");

doc.Save(ArtifactsDir + "Font.LocaleId.docx");
```

### Ver también

* class [Font](../)
* espacio de nombres [Aspose.Words](../../font/)
* asamblea [Aspose.Words](../../../)


