---
title: OdsoFieldMapDataCollection.RemoveAt
second_title: Referencia de API de Aspose.Words para .NET
description: OdsoFieldMapDataCollection método. Elimina el elemento en el índice especificado.
type: docs
weight: 70
url: /es/net/aspose.words.settings/odsofieldmapdatacollection/removeat/
---
## OdsoFieldMapDataCollection.RemoveAt method

Elimina el elemento en el índice especificado.

```csharp
public void RemoveAt(int index)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| index | Int32 | El índice de base cero del elemento. |

### Ejemplos

Muestra cómo acceder a la colección de datos que asigna columnas de fuentes de datos a campos combinados.

```csharp
Document doc = new Document(MyDir + "Odso data.docx");

// Esta colección define cómo una combinación de correo mapeará las columnas de una fuente de datos
// a los campos MERGEFIELD, ADRESSBLOCK y GREETINGLINE predefinidos.
OdsoFieldMapDataCollection dataCollection = doc.MailMergeSettings.Odso.FieldMapDatas;
Assert.AreEqual(30, dataCollection.Count);

using (IEnumerator<OdsoFieldMapData> enumerator = dataCollection.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Field map data index {index++}, type \"{enumerator.Current.Type}\":");

        Console.WriteLine(
            enumerator.Current.Type != OdsoFieldMappingType.Null
                ? $"\tColumn \"{enumerator.Current.Name}\", number {enumerator.Current.Column} mapped to merge field \"{enumerator.Current.MappedName}\"."
                : "\tNo valid column to field mapping data present.");
    }
}

// Clona los elementos de esta colección.
Assert.AreNotEqual(dataCollection[0], dataCollection[0].Clone());

// Usar los elementos del método "RemoveAt" individualmente por índice.
dataCollection.RemoveAt(0);

Assert.AreEqual(29, dataCollection.Count);

// Use el método "Borrar" para borrar toda la colección a la vez.
dataCollection.Clear();

Assert.AreEqual(0, dataCollection.Count);
```

### Ver también

* class [OdsoFieldMapDataCollection](../)
* espacio de nombres [Aspose.Words.Settings](../../odsofieldmapdatacollection/)
* asamblea [Aspose.Words](../../../)


