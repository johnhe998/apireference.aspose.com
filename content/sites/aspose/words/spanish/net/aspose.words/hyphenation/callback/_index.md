---
title: Hyphenation.Callback
second_title: Referencia de API de Aspose.Words para .NET
description: Hyphenation propiedad. Obtiene o establece la interfaz de devolución de llamada utilizada para solicitar diccionarios cuando se crea el diseño de página del documento. Esto permite retrasar la carga de diccionarios lo que puede ser útil cuando se procesan documentos en muchos idiomas.
type: docs
weight: 10
url: /es/net/aspose.words/hyphenation/callback/
---
## Hyphenation.Callback property

Obtiene o establece la interfaz de devolución de llamada utilizada para solicitar diccionarios cuando se crea el diseño de página del documento. Esto permite retrasar la carga de diccionarios, lo que puede ser útil cuando se procesan documentos en muchos idiomas.

```csharp
public static IHyphenationCallback Callback { get; set; }
```

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

* interface [IHyphenationCallback](../../ihyphenationcallback/)
* class [Hyphenation](../)
* espacio de nombres [Aspose.Words](../../hyphenation/)
* asamblea [Aspose.Words](../../../)


