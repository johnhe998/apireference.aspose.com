---
title: Interface IFieldUpdateCultureProvider
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fields.IFieldUpdateCultureProvider interfaz. Cuando se implementa proporciona unaCultureInfo objeto que debe usarse durante la actualización de un campo en particular.
type: docs
weight: 2540
url: /es/net/aspose.words.fields/ifieldupdatecultureprovider/
---
## IFieldUpdateCultureProvider interface

Cuando se implementa, proporciona unaCultureInfo objeto que debe usarse durante la actualización de un campo en particular.

```csharp
public interface IFieldUpdateCultureProvider
```

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetCulture](../../aspose.words.fields/ifieldupdatecultureprovider/getculture/)(string, Field) | Devuelve unCultureInfo objeto a utilizar durante la actualización del campo. |

### Ejemplos

Muestra cómo especificar una referencia cultural que analiza el formato de fecha/hora para cada campo.

```csharp
[Test]
public void DefineDateTimeFormatting()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.InsertField(FieldType.FieldTime, true);

    doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

    // Establecer un proveedor que devuelva un objeto cultural específico para cada campo.
    doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

    FieldTime fieldDate = (FieldTime)doc.Range.Fields[0];
    if (fieldDate.LocaleId != (int)EditingLanguage.Russian)
        fieldDate.LocaleId = (int)EditingLanguage.Russian;

    doc.Save(ArtifactsDir + "FieldOptions.UpdateDateTimeFormatting.pdf");
}

/// <summary>
/// Proporciona un objeto CultureInfo que debe usarse durante la actualización de un campo.
/// </summary>
private class FieldUpdateCultureProvider : IFieldUpdateCultureProvider
{
    /// <summary>
    /// Devuelve un objeto CultureInfo para ser utilizado durante la actualización del campo.
    /// </summary>
    public CultureInfo GetCulture(string name, Field field)
    {
        switch (name)
        {
            case "ru-RU":
                CultureInfo culture = new CultureInfo(name, false);
                DateTimeFormatInfo format = culture.DateTimeFormat;

                format.MonthNames = new[] { "месяц 1", "месяц 2", "месяц 3", "месяц 4", "месяц 5", "месяц 6", "месяц 7", "месяц 8", "месяц 9", "месяц 10", "месяц 11", "месяц 12", "" };
                format.MonthGenitiveNames = format.MonthNames;
                format.AbbreviatedMonthNames = new[] { "мес 1", "мес 2", "мес 3", "мес 4", "мес 5", "мес 6", "мес 7", "мес 8", "мес 9", "мес 10", "мес 11", "мес 12", "" };
                format.AbbreviatedMonthGenitiveNames = format.AbbreviatedMonthNames;

                format.DayNames = new[] { "день недели 7", "день недели 1", "день недели 2", "день недели 3", "день недели 4", "день недели 5", "день недели 6" };
                format.AbbreviatedDayNames = new[] { "день 7", "день 1", "день 2", "день 3", "день 4", "день 5", "день 6" };
                format.ShortestDayNames = new[] { "д7", "д1", "д2", "д3", "д4", "д5", "д6" };

                format.AMDesignator = "До полудня";
                format.PMDesignator = "После полудня";

                const string pattern = "yyyy MM (MMMM) dd (dddd) hh:mm:ss tt";
                format.LongDatePattern = pattern;
                format.LongTimePattern = pattern;
                format.ShortDatePattern = pattern;
                format.ShortTimePattern = pattern;

                return culture;
            case "en-US":
                return new CultureInfo(name, false);
            default:
                return null;
        }
    }
}
```

### Ver también

* espacio de nombres [Aspose.Words.Fields](../../aspose.words.fields/)
* asamblea [Aspose.Words](../../)


