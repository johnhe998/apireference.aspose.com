---
title: Hyphenation.UnregisterDictionary
second_title: Referencia de API de Aspose.Words para .NET
description: Hyphenation método. Anula el registro de un diccionario de separación de palabras para el idioma especificado.
type: docs
weight: 50
url: /es/net/aspose.words/hyphenation/unregisterdictionary/
---
## Hyphenation.UnregisterDictionary method

Anula el registro de un diccionario de separación de palabras para el idioma especificado.

Esto es diferente de registrar un diccionario nulo. Anular el registro de un diccionario habilita la devolución de llamada para el idioma especificado.

```csharp
public static void UnregisterDictionary(string language)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| language | String | Un nombre de idioma, por ejemplo, "en-US". Consulte la documentación de .NET para "nombre cultural" y RFC 4646 para obtener detalles. |

### Ejemplos

Muestra cómo registrar un diccionario de separación silábica.

```csharp
// Un diccionario de separación de palabras contiene una lista de cadenas que definen las reglas de separación de palabras para el idioma del diccionario.
// Cuando un documento contiene líneas de texto en las que una palabra se puede dividir y continuar en la siguiente línea,
// la división de guiones buscará en la lista de cadenas del diccionario las subcadenas de esa palabra.
// Si el diccionario contiene una subcadena, la partición dividirá la palabra en dos líneas
// por la subcadena y agregue un guión a la primera mitad.
// Registre un archivo de diccionario del sistema de archivos local en la configuración regional "de-CH".
Hyphenation.RegisterDictionary("de-CH", MyDir + "hyph_de_CH.dic");

Assert.True(Hyphenation.IsDictionaryRegistered("de-CH"));

// Abra un documento que contenga texto con una configuración regional que coincida con la de nuestro diccionario,
// y guárdelo en un formato de guardado de página fija. El texto de ese documento se dividirá con guión.
Document doc = new Document(MyDir + "German text.docx");

Assert.True(doc.FirstSection.Body.FirstParagraph.Runs.OfType<Run>().All(
    r => r.Font.LocaleId == new CultureInfo("de-CH").LCID));

doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Registered.pdf");

// Vuelva a cargar el documento después de cancelar el registro del diccionario,
// y guárdelo en otro PDF, que no tendrá texto con guión.
Hyphenation.UnregisterDictionary("de-CH");

Assert.False(Hyphenation.IsDictionaryRegistered("de-CH"));

doc = new Document(MyDir + "German text.docx");
doc.Save(ArtifactsDir + "Hyphenation.Dictionary.Unregistered.pdf");
```

### Ver también

* class [Hyphenation](../)
* espacio de nombres [Aspose.Words](../../hyphenation/)
* asamblea [Aspose.Words](../../../)


