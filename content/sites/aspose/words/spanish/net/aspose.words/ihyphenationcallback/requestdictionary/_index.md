---
title: IHyphenationCallback.RequestDictionary
second_title: Referencia de API de Aspose.Words para .NET
description: IHyphenationCallback método. Notifica a la aplicación que no se encontró el diccionario de partición de palabras para el idioma especificado y es posible que deba registrarse.
type: docs
weight: 10
url: /es/net/aspose.words/ihyphenationcallback/requestdictionary/
---
## IHyphenationCallback.RequestDictionary method

Notifica a la aplicación que no se encontró el diccionario de partición de palabras para el idioma especificado y es posible que deba registrarse.

La implementación debe encontrar un diccionario y registrarlo usando[`RegisterDictionary`](../../hyphenation/registerdictionary/)métodos.

Si el diccionario no está disponible para la implementación del idioma especificado, puede optar por no recibir más llamadas para el mismo idioma usando[`RegisterDictionary`](../../hyphenation/registerdictionary/) con valor nulo.

```csharp
public void RequestDictionary(string language)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| language | String | Un nombre de idioma, por ejemplo, "en-US". Consulte la documentación de .NET para "nombre cultural" y RFC 4646 para obtener detalles. |

### Observaciones

Las excepciones lanzadas por este método cancelarán la ejecución del proceso de diseño de página.

### Ejemplos

Muestra cómo abrir y registrar un diccionario desde un archivo.

```csharp
{
    // Configure una devolución de llamada que rastree las advertencias que ocurren durante el registro del diccionario de división de palabras.
    WarningInfoCollection warningInfoCollection = new WarningInfoCollection();
    Hyphenation.WarningCallback = warningInfoCollection;

    // Registre un diccionario de partición de palabras en inglés (EE. UU.) por transmisión.
    Stream dictionaryStream = new FileStream(MyDir + "hyph_en_US.dic", FileMode.Open);
    Hyphenation.RegisterDictionary("en-US", dictionaryStream);

    Assert.AreEqual(0, warningInfoCollection.Count);

    // Abra un documento con una configuración regional que Microsoft Word no pueda separar con guiones en una máquina en inglés, como el alemán.
    Document doc = new Document(MyDir + "German text.docx");

    // Para dividir ese documento al guardarlo, necesitamos un diccionario de partición para el código de idioma "de-CH".
    // Esta devolución de llamada manejará la solicitud automática de ese diccionario.
    Hyphenation.Callback = new CustomHyphenationDictionaryRegister();

    // Cuando guardemos el documento, la separación de palabras en alemán tendrá efecto.
    doc.Save(ArtifactsDir + "Hyphenation.RegisterDictionary.pdf");

    // Este diccionario contiene dos patrones idénticos, lo que activará una advertencia.
    Assert.AreEqual(1, warningInfoCollection.Count);
    Assert.AreEqual(WarningType.MinorFormattingLoss, warningInfoCollection[0].WarningType);
    Assert.AreEqual(WarningSource.Layout, warningInfoCollection[0].Source);
    Assert.AreEqual("Hyphenation dictionary contains duplicate patterns. The only first found pattern will be used. " +
                    "Content can be wrapped differently.", warningInfoCollection[0].Description);
}

/// <summary>
/// Asocia códigos de idioma ISO con nombres de archivo del sistema local para archivos de diccionario de división de palabras.
/// </summary>
private class CustomHyphenationDictionaryRegister : IHyphenationCallback
{
    public CustomHyphenationDictionaryRegister()
    {
        mHyphenationDictionaryFiles = new Dictionary<string, string>
        {
            { "en-US", MyDir + "hyph_en_US.dic" },
            { "de-CH", MyDir + "hyph_de_CH.dic" }
        };
    }

    public void RequestDictionary(string language)
    {
        Console.Write("Hyphenation dictionary requested: " + language);

        if (Hyphenation.IsDictionaryRegistered(language))
        {
            Console.WriteLine(", is already registered.");
            return;
        }

        if (mHyphenationDictionaryFiles.ContainsKey(language))
        {
            Hyphenation.RegisterDictionary(language, mHyphenationDictionaryFiles[language]);
            Console.WriteLine(", successfully registered.");
            return;
        }

        Console.WriteLine(", no respective dictionary file known by this Callback.");
    }

    private readonly Dictionary<string, string> mHyphenationDictionaryFiles;
}
```

### Ver también

* interface [IHyphenationCallback](../)
* espacio de nombres [Aspose.Words](../../ihyphenationcallback/)
* asamblea [Aspose.Words](../../../)


