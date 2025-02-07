---
title: Enum OdsoDataSourceType
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Settings.OdsoDataSourceType enum. Specifica il tipo di origine dati esterna a cui connettersi come parte delle informazioni di connessione ODSO.
type: docs
weight: 5590
url: /it/net/aspose.words.settings/odsodatasourcetype/
---
## OdsoDataSourceType enumeration

Specifica il tipo di origine dati esterna a cui connettersi come parte delle informazioni di connessione ODSO.

```csharp
public enum OdsoDataSourceType
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Text | `0` | Specifica che un determinato documento è stato connesso a un file di testo. Possibilmente wdMergeSubTypeOther. |
| Database | `1` | Specifica che un determinato documento è stato connesso a un database. Possibilmente wdMergeSubTypeAccess. |
| AddressBook | `2` | Specifica che un determinato documento è stato collegato a una rubrica di contatti. Possibilmente wdMergeSubTypeOAL. |
| Document1 | `3` | Specifica che un determinato documento è stato connesso a un altro formato di documento supportato dall'applicazione di produzione. Possibilmente wdMergeSubTypeOLEDBWord. |
| Document2 | `4` | Specifica che un determinato documento è stato connesso a un altro formato di documento supportato dall'applicazione di produzione. Possibilmente wdMergeSubTypeWorks. |
| Native | `5` | Specifica che un determinato documento è stato connesso a un altro formato di documento nativo dell'applicazione di produzione. Possibilmente wdMergeSubTypeOLEDBText |
| Email | `6` | Specifica che un determinato documento è stato connesso a un'applicazione di posta elettronica. Possibilmente wdMergeSubTypeOutlook. |
| None | `7` | Il tipo dell'origine dati esterna non è specificato. Possibilmente wdMergeSubTypeWord. |
| Legacy | `8` | Specifica che un determinato documento è stato connesso a un formato di documento legacy supportato dall'applicazione di produzione Possibilmente wdMergeSubTypeWord2000. |
| Master | `9` | Specifica che un determinato documento è stato connesso a un'origine dati che aggrega altre origini dati. |
| Default | `7` | Uguale aNone . |

### Osservazioni

La specifica OOXML è molto vaga per questa enumerazione. Immagino che potrebbe corrispondere all'enumerazione WdMergeSubType http://msdn.microsoft.com/en-us/library/bb237801.aspx.

### Esempi

Mostra come eseguire una stampa unione con i dati di un oggetto origine dati di Office.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");
builder.Writeln(": ");
builder.InsertField("MERGEFIELD Message", "<Message>");

// Crea un'origine dati sotto forma di file ASCII, con "|" carattere
// funge da delimitatore che separa le colonne. La prima riga contiene i nomi delle tre colonne,
// e ogni riga successiva è una riga con i rispettivi valori.
string[] lines = { "FirstName|LastName|Message",
    "John|Doe|Hello! This message was created with Aspose Words mail merge." };
string dataSrcFilename = ArtifactsDir + "MailMerge.MailMergeSettings.DataSource.txt";

File.WriteAllLines(dataSrcFilename, lines);

MailMergeSettings settings = doc.MailMergeSettings;
settings.MainDocumentType = MailMergeMainDocumentType.MailingLabels;
settings.CheckErrors = MailMergeCheckErrors.Simulate;
settings.DataType = MailMergeDataType.Native;
settings.DataSource = dataSrcFilename;
settings.Query = "SELECT * FROM " + doc.MailMergeSettings.DataSource;
settings.LinkToQuery = true;
settings.ViewMergedData = true;

Assert.AreEqual(MailMergeDestination.Default, settings.Destination);
Assert.False(settings.DoNotSupressBlankLines);

Odso odso = settings.Odso;
odso.DataSource = dataSrcFilename;
odso.DataSourceType = OdsoDataSourceType.Text;
odso.ColumnDelimiter = '|';
odso.FirstRowContainsColumnNames = true;

Assert.AreNotSame(odso, odso.Clone());
Assert.AreNotSame(settings, settings.Clone());

// L'apertura di questo documento in Microsoft Word eseguirà la stampa unione prima di visualizzare il contenuto. 
doc.Save(ArtifactsDir + "MailMerge.MailMergeSettings.docx");
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Settings](../../aspose.words.settings/)
* assemblea [Aspose.Words](../../)


