---
title: Style.LinkedStyleName
second_title: Référence de l'API Aspose.Words pour .NET
description: Style propriété. Récupère le nom du Style lié à celuici. Renvoie une chaîne vide si aucun style nest lié.
type: docs
weight: 80
url: /fr/net/aspose.words/style/linkedstylename/
---
## Style.LinkedStyleName property

Récupère le nom du Style lié à celui-ci. Renvoie une chaîne vide si aucun style n'est lié.

```csharp
public string LinkedStyleName { get; }
```

### Exemples

Montre comment utiliser les alias de style.

```csharp
Document doc = new Document(MyDir + "Style with alias.docx");

// Ce document contient un style nommé "MonStyle,MonStyle Alias 1,MonStyle Alias 2".
// Si le nom d'un style a plusieurs valeurs séparées par des virgules, chaque clause est un alias distinct.
Style style = doc.Styles["MyStyle"];
Assert.AreEqual(new [] { "MyStyle Alias 1", "MyStyle Alias 2" }, style.Aliases);
Assert.AreEqual("Title", style.BaseStyleName);
Assert.AreEqual("MyStyle Char", style.LinkedStyleName);

// Nous pouvons référencer un style en utilisant son alias, ainsi que son nom.
Assert.AreEqual(doc.Styles["MyStyle Alias 1"], doc.Styles["MyStyle Alias 2"]);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.ParagraphFormat.Style = doc.Styles["MyStyle Alias 1"];
builder.Writeln("Hello world!");
builder.ParagraphFormat.Style = doc.Styles["MyStyle Alias 2"];
builder.Write("Hello again!");

Assert.AreEqual(doc.FirstSection.Body.Paragraphs[0].ParagraphFormat.Style, 
    doc.FirstSection.Body.Paragraphs[1].ParagraphFormat.Style);
```

### Voir également

* class [Style](../)
* espace de noms [Aspose.Words](../../style/)
* Assemblée [Aspose.Words](../../../)


