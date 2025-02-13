---
title: FieldGreetingLine.AlternateText
second_title: Aspose.Words für .NET-API-Referenz
description: FieldGreetingLine eigendom. Ruft den Text ab oder legt ihn fest der in das Feld aufgenommen werden soll wenn der Name leer ist.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldgreetingline/alternatetext/
---
## FieldGreetingLine.AlternateText property

Ruft den Text ab oder legt ihn fest, der in das Feld aufgenommen werden soll, wenn der Name leer ist.

```csharp
public string AlternateText { get; set; }
```

### Beispiele

Zeigt, wie ein GREETINGLINE-Feld eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine generische Begrüßung mit einem GREETINGLINE-Feld und etwas Text danach.
FieldGreetingLine field = (FieldGreetingLine)builder.InsertField(FieldType.FieldGreetingLine, true);
builder.Writeln("\n\n\tThis is your custom greeting, created programmatically using Aspose Words!");

// Ein GREETINGLINE-Feld akzeptiert Werte aus einer Datenquelle während eines Seriendrucks, wie ein MERGEFIELD.
// Es kann auch formatieren, wie die Daten der Quelle an ihrer Stelle geschrieben werden, sobald der Seriendruck abgeschlossen ist.
// Die Sammlung der Feldnamen entspricht den Spalten aus der Datenquelle
// von dem das Feld Werte annehmen wird.
Assert.AreEqual(0, field.GetFieldNames().Length);

// Um dieses Array zu füllen, müssen wir ein Format für unsere Begrüßungszeile angeben.
field.NameFormat = "<< _BEFORE_ Dear >><< _TITLE0_ >><< _LAST0_ >><< _AFTER_ ,>> ";

// Jetzt akzeptiert unser Feld Werte aus diesen beiden Spalten in der Datenquelle.
Assert.AreEqual("Courtesy Title", field.GetFieldNames()[0]);
Assert.AreEqual("Last Name", field.GetFieldNames()[1]);
Assert.AreEqual(2, field.GetFieldNames().Length);

// Dieser String deckt alle Fälle ab, in denen die Daten der Datentabelle ungültig sind
// durch Ersetzen des fehlerhaften Namens durch einen String.
field.AlternateText = "Sir or Madam";

// Legen Sie ein Gebietsschema fest, um das Ergebnis zu formatieren.
field.LanguageId = new CultureInfo("en-US").LCID.ToString();

Assert.AreEqual(" GREETINGLINE  \\f \"<< _BEFORE_ Dear >><< _TITLE0_ >><< _LAST0_ >><< _AFTER_ ,>> \" \\e \"Sir or Madam\" \\l 1033", 
    field.GetFieldCode());

// Erstellen Sie eine Datentabelle mit Spalten, deren Namen mit Elementen übereinstimmen
// aus der Sammlung der Feldnamen des Felds und führen Sie dann den Seriendruck durch.
DataTable table = new DataTable("Employees");
table.Columns.Add("Courtesy Title");
table.Columns.Add("First Name");
table.Columns.Add("Last Name");
table.Rows.Add("Mr.", "John", "Doe");
table.Rows.Add("Mrs.", "Jane", "Cardholder");

// Diese Zeile hat einen ungültigen Wert in der Spalte Höflichkeitstitel, daher wird unsere Begrüßung standardmäßig den alternativen Text verwenden.
table.Rows.Add("", "No", "Name");

doc.MailMerge.Execute(table);

Assert.That(doc.Range.Fields, Is.Empty);
Assert.AreEqual("Dear Mr. Doe,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!\r" +
                "\fDear Mrs. Cardholder,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!\r" +
                "\fDear Sir or Madam,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!",
    doc.GetText().Trim());
```

### Siehe auch

* class [FieldGreetingLine](../)
* namensraum [Aspose.Words.Fields](../../fieldgreetingline/)
* Montage [Aspose.Words](../../../)


