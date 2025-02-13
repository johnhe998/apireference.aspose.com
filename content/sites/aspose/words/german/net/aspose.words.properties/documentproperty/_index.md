---
title: Class DocumentProperty
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Properties.DocumentProperty klas. Repräsentiert eine benutzerdefinierte oder integrierte Dokumenteigenschaft.
type: docs
weight: 4220
url: /de/net/aspose.words.properties/documentproperty/
---
## DocumentProperty class

Repräsentiert eine benutzerdefinierte oder integrierte Dokumenteigenschaft.

```csharp
public class DocumentProperty
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [IsLinkToContent](../../aspose.words.properties/documentproperty/islinktocontent/) { get; } | Zeigt an, ob diese Eigenschaft mit Inhalt verknüpft ist oder nicht. |
| [LinkSource](../../aspose.words.properties/documentproperty/linksource/) { get; } | Ruft die Quelle einer verknüpften benutzerdefinierten Dokumenteigenschaft ab. |
| [Name](../../aspose.words.properties/documentproperty/name/) { get; } | Gibt den Namen der Eigenschaft zurück. |
| [Type](../../aspose.words.properties/documentproperty/type/) { get; } | Ruft den Datentyp der Eigenschaft ab. |
| [Value](../../aspose.words.properties/documentproperty/value/) { get; set; } | Ruft den Wert der Eigenschaft ab oder legt ihn fest. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [ToBool](../../aspose.words.properties/documentproperty/tobool/)() | Gibt den Eigenschaftswert als bool zurück. |
| [ToByteArray](../../aspose.words.properties/documentproperty/tobytearray/)() | Gibt den Eigenschaftswert als Byte-Array zurück. |
| [ToDateTime](../../aspose.words.properties/documentproperty/todatetime/)() | Gibt den Eigenschaftswert als DateTime in UTC zurück. |
| [ToDouble](../../aspose.words.properties/documentproperty/todouble/)() | Gibt den Eigenschaftswert als Double zurück. |
| [ToInt](../../aspose.words.properties/documentproperty/toint/)() | Gibt den Eigenschaftswert als ganze Zahl zurück. |
| override [ToString](../../aspose.words.properties/documentproperty/tostring/)() | Gibt den Eigenschaftswert als Zeichenfolge zurück, die gemäß dem aktuellen Gebietsschema formatiert ist. |

### Beispiele

Zeigt, wie Sie mit integrierten Dokumenteigenschaften arbeiten.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// Das "Document"-Objekt enthält einige seiner Metadaten in seinen Mitgliedern.
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// Das Dokument speichert auch Metadaten in seinen eingebauten Eigenschaften.
// Jede eingebaute Eigenschaft ist ein Mitglied des "BuiltInDocumentProperties"-Objekts des Dokuments.
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // Einige Eigenschaften können mehrere Werte speichern.
    if (docProperty.Value is ICollection<object>)
    {
        foreach (object value in docProperty.Value as ICollection<object>)
            Console.WriteLine($"\tValue:\t\"{value}\"");
    }
    else
    {
        Console.WriteLine($"\tValue:\t\"{docProperty.Value}\"");
    }
}
```

### Siehe auch

* class [DocumentPropertyCollection](../documentpropertycollection/)
* namensraum [Aspose.Words.Properties](../../aspose.words.properties/)
* Montage [Aspose.Words](../../)


