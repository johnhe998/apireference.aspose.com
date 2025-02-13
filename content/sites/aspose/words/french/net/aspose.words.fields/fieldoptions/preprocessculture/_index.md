---
title: FieldOptions.PreProcessCulture
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldOptions propriété. Obtient ou définit la culture pour prétraiter les valeurs de champ.
type: docs
weight: 150
url: /fr/net/aspose.words.fields/fieldoptions/preprocessculture/
---
## FieldOptions.PreProcessCulture property

Obtient ou définit la culture pour prétraiter les valeurs de champ.

```csharp
public CultureInfo PreProcessCulture { get; set; }
```

### Remarques

Actuellement, cette propriété n'affecte que la valeur du[`FieldDocProperty`](../../fielddocproperty/) champ.

La valeur par défaut est **nul** . Lorsque cette propriété est définie sur **nul** , la[`FieldDocProperty`](../../fielddocproperty/) la valeur du champ est preprocessed avec la culture contrôlée par le[`FieldUpdateCultureSource`](../fieldupdateculturesource/) propriété.

### Exemples

Montre comment définir la culture de prétraitement.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Définir la culture selon laquelle certains champs formateront leurs valeurs affichées.
doc.FieldOptions.PreProcessCulture = new CultureInfo("de-DE");

Field field = builder.InsertField(" DOCPROPERTY CreateTime");

// Le champ DOCPROPERTY affichera son résultat formaté selon la culture de prétraitement
// nous avons défini l'allemand. Le champ affichera la date/heure au format "jj.mm.aaaa hh:mm".
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[.]\d{2}[.]\d{4} \d{2}[:]\d{2}").Success);

doc.FieldOptions.PreProcessCulture = CultureInfo.InvariantCulture;
field.Update();

// Après être passé à la culture invariante, le champ DOCPROPERTY utilisera le format "mm/dd/yyyy hh:mm".
Assert.IsTrue(Regex.Match(field.Result, @"\d{2}[/]\d{2}[/]\d{4} \d{2}[:]\d{2}").Success);
```

### Voir également

* class [FieldOptions](../)
* espace de noms [Aspose.Words.Fields](../../fieldoptions/)
* Assemblée [Aspose.Words](../../../)


