---
title: Class Hyphenation
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Hyphenation clase. Proporciona métodos para trabajar con diccionarios de guiones. Estos diccionarios prescriben dónde se pueden unir palabras de un idioma específico.
type: docs
weight: 2970
url: /es/net/aspose.words/hyphenation/
---
## Hyphenation class

Proporciona métodos para trabajar con diccionarios de guiones. Estos diccionarios prescriben dónde se pueden unir palabras de un idioma específico.

```csharp
public static class Hyphenation
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| static [Callback](../../aspose.words/hyphenation/callback/) { get; set; } | Obtiene o establece la interfaz de devolución de llamada utilizada para solicitar diccionarios cuando se crea el diseño de página del documento. Esto permite retrasar la carga de diccionarios, lo que puede ser útil cuando se procesan documentos en muchos idiomas. |
| static [WarningCallback](../../aspose.words/hyphenation/warningcallback/) { get; set; } | Llamado durante una carga de patrones de separación silábica, cuando se detecta un problema que podría resultar en la pérdida de fidelidad del formato. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| static [IsDictionaryRegistered](../../aspose.words/hyphenation/isdictionaryregistered/)(string) | Devuelve Falso si para el idioma especificado no hay ningún diccionario registrado o si el diccionario registrado es Nulo, de lo contrario, es Verdadero. |
| static [RegisterDictionary](../../aspose.words/hyphenation/registerdictionary/#registerdictionary)(string, Stream) | Registra y carga un diccionario de división de palabras para el idioma especificado desde una secuencia. Se lanza si el diccionario no se puede leer o tiene un formato no válido. |
| static [RegisterDictionary](../../aspose.words/hyphenation/registerdictionary/#registerdictionary_1)(string, string) | Registra y carga un diccionario de división de palabras para el idioma especificado desde el archivo. Se lanza si el diccionario no se puede leer o tiene un formato no válido. |
| static [UnregisterDictionary](../../aspose.words/hyphenation/unregisterdictionary/)(string) | Anula el registro de un diccionario de separación de palabras para el idioma especificado. |

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

* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


