---
title: DocumentBuilder.InsertTextInput
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder methode. Fügt ein Textformularfeld an der aktuellen Position ein.
type: docs
weight: 450
url: /de/net/aspose.words/documentbuilder/inserttextinput/
---
## DocumentBuilder.InsertTextInput method

Fügt ein Textformularfeld an der aktuellen Position ein.

```csharp
public FormField InsertTextInput(string name, TextFormFieldType type, string format, 
    string fieldValue, int maxLength)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| name | String | Der Name des Formularfelds. Kann eine leere Zeichenfolge sein. |
| type | TextFormFieldType | Gibt den Typ des Textformularfelds an. |
| format | String | Formatzeichenfolge, die zum Formatieren des Werts des Formularfelds verwendet wird. |
| fieldValue | String | Text, der im Feld angezeigt wird. |
| maxLength | Int32 | Maximale Länge, die der Benutzer in das Formularfeld eingeben kann. Für unbegrenzte Länge auf Null setzen. |

### Rückgabewert

Der gerade eingefügte Formularfeldknoten.

### Bemerkungen

Wenn Sie einen Namen für das Formularfeld angeben, wird automatisch ein Lesezeichen mit demselben Namen erstellt.

### Beispiele

Zeigt, wie Sie ein Texteingabeformularfeld in ein Dokument einfügen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Formular ein, das den Benutzer auffordert, Text einzugeben.
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Enter your text here", 0);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTextInput.docx");
```

Zeigt, wie ein Texteingabeformularfeld eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please enter text here: ");

// Fügen Sie ein Texteingabefeld ein, das es dem Benutzer ermöglicht, darauf zu klicken und Text einzugeben.
// Einen Platzhaltertext zuweisen, den der Benutzer überschreiben und übergeben kann
// eine maximale Textlänge von 0, um den Inhalt des Formularfelds nicht zu begrenzen.
builder.InsertTextInput("TextInput1", TextFormFieldType.Regular, "", "Placeholder text", 0);

// Das Formularfeld erscheint in Form eines "input"-HTML-Tags mit einer Art "Text".
doc.Save(ArtifactsDir + "FormFields.TextInput.html");
```

Zeigt, wie Formularfelder erstellt werden.

```csharp
DocumentBuilder builder = new DocumentBuilder();

// Formularfelder sind Objekte im Dokument, mit denen der Benutzer interagieren kann, indem er zur Eingabe von Werten aufgefordert wird.
// Wir können sie mit einem Document Builder erstellen, und unten sind zwei Möglichkeiten, dies zu tun.
// 1 - Einfache Texteingabe:
builder.InsertTextInput("My text input", TextFormFieldType.Regular, 
    "", "Enter your name here", 30);

// 2 - Kombinationsfeld mit Aufforderungstext und einer Reihe möglicher Werte:
string[] items =
{
    "-- Select your favorite footwear --", "Sneakers", "Oxfords", "Flip-flops", "Other"
};

builder.InsertParagraph();
builder.InsertComboBox("My combo box", items, 0);

builder.Document.Save(ArtifactsDir + "DocumentBuilder.CreateForm.docx");
```

### Siehe auch

* class [FormField](../../../aspose.words.fields/formfield/)
* enum [TextFormFieldType](../../../aspose.words.fields/textformfieldtype/)
* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


