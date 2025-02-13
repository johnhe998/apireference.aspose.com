---
title: StyleCollection.Add
second_title: Aspose.Words für .NET-API-Referenz
description: StyleCollection methode. Erstellt einen neuen benutzerdefinierten Stil und fügt ihn der Sammlung hinzu.
type: docs
weight: 60
url: /de/net/aspose.words/stylecollection/add/
---
## StyleCollection.Add method

Erstellt einen neuen benutzerdefinierten Stil und fügt ihn der Sammlung hinzu.

```csharp
public Style Add(StyleType type, string name)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| type | StyleType | EIN[`StyleType`](../../styletype/) -Wert, der den Typ des zu erstellenden Stils angibt. |
| name | String | Groß-/Kleinschreibung beachtender Name des zu erstellenden Stils. |

### Bemerkungen

Sie können Zeichen-, Absatz- oder Listenstile erstellen.

Beim Erstellen eines Listenstils wird der Stil mit der standardmäßigen nummerierten Listenformatierung (1 \ a \ i) erstellt.

Löst eine Ausnahme aus, wenn ein Stil mit diesem Namen bereits vorhanden ist.

### Beispiele

Zeigt, wie Sie der Stilsammlung eines Dokuments einen Stil hinzufügen.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// Legen Sie Standardparameter für neue Stile fest, die wir später zu dieser Sammlung hinzufügen können.
styles.DefaultFont.Name = "Courier New";

// Wenn wir einen Stil des "StyleType.Paragraph" hinzufügen, wendet die Sammlung die Werte von an
// seine "DefaultParagraphFormat"-Eigenschaft auf die "ParagraphFormat"-Eigenschaft des Stils.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// Füge einen Stil hinzu und vergewissere dich, dass er die Standardeinstellungen hat.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

Zeigt, wie ein Listenstil erstellt und in einem Dokument verwendet wird.

```csharp
Document doc = new Document();

// Eine Liste ermöglicht es uns, Sätze von Absätzen mit Präfixsymbolen und Einzügen zu organisieren und zu dekorieren.
// Wir können verschachtelte Listen erstellen, indem wir die Einrückungsebene erhöhen. 
// Wir können eine Liste beginnen und beenden, indem wir die "ListFormat"-Eigenschaft eines Dokumentenerstellers verwenden. 
// Jeder Absatz, den wir zwischen dem Anfang und dem Ende einer Liste hinzufügen, wird zu einem Element in der Liste.
// Wir können ein ganzes List-Objekt in einem Stil enthalten.
Style listStyle = doc.Styles.Add(StyleType.List, "MyListStyle");

List list1 = listStyle.List;

Assert.True(list1.IsListStyleDefinition);
Assert.False(list1.IsListStyleReference);
Assert.True(list1.IsMultiLevel);
Assert.AreEqual(listStyle, list1.Style);

// Ändern Sie das Aussehen aller Listenebenen in unserer Liste.
foreach (ListLevel level in list1.ListLevels)
{
    level.Font.Name = "Verdana";
    level.Font.Color = Color.Blue;
    level.Font.Bold = true;
}

DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Using list style first time:");

// Eine weitere Liste aus einer Liste innerhalb eines Stils erstellen.
List list2 = doc.Lists.Add(listStyle);

Assert.False(list2.IsListStyleDefinition);
Assert.True(list2.IsListStyleReference);
Assert.AreEqual(listStyle, list2.Style);

// Fügen Sie einige Listenelemente hinzu, die unsere Liste formatieren wird.
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Writeln("Using list style second time:");

// Eine weitere Liste basierend auf dem Listenstil erstellen und anwenden.
List list3 = doc.Lists.Add(listStyle);
builder.ListFormat.List = list3;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(ArtifactsDir + "Lists.CreateAndUseListStyle.docx");
```

### Siehe auch

* class [Style](../../style/)
* enum [StyleType](../../styletype/)
* class [StyleCollection](../)
* namensraum [Aspose.Words](../../stylecollection/)
* Montage [Aspose.Words](../../../)


