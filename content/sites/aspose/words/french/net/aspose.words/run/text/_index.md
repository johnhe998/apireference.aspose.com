---
title: Run.Text
second_title: Référence de l'API Aspose.Words pour .NET
description: Run propriété. Obtient ou définit le texte de lexécution.
type: docs
weight: 30
url: /fr/net/aspose.words/run/text/
---
## Run.Text property

Obtient ou définit le texte de l'exécution.

```csharp
public string Text { get; set; }
```

### Exemples

Montre comment construire un document Aspose.Words à la main.

```csharp
Document doc = new Document();

// Un document vierge contient une section, un corps et un paragraphe.
// Appelez la méthode "RemoveAllChildren" pour supprimer tous ces nœuds,
// et se retrouver avec un nœud de document sans enfants.
doc.RemoveAllChildren();

// Ce document n'a plus de nœuds enfants composites auxquels nous pouvons ajouter du contenu.
// Si nous souhaitons l'éditer, nous devrons repeupler sa collection de nœuds.
// Tout d'abord, créez une nouvelle section, puis ajoutez-la en tant qu'enfant au nœud de document racine.
Section section = new Section(doc);
doc.AppendChild(section);

// Définit certaines propriétés de mise en page pour la section.
section.PageSetup.SectionStart = SectionStart.NewPage;
section.PageSetup.PaperSize = PaperSize.Letter;

// Une section a besoin d'un corps, qui contiendra et affichera tout son contenu
// sur la page entre l'en-tête et le pied de page de la section.
Body body = new Body(doc);
section.AppendChild(body);

// Crée un paragraphe, définit certaines propriétés de formatage, puis l'ajoute en tant qu'enfant au corps.
Paragraph para = new Paragraph(doc);

para.ParagraphFormat.StyleName = "Heading 1";
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;

body.AppendChild(para);

// Enfin, ajoutez du contenu pour faire le document. Créer une course,
// définit son apparence et son contenu, puis l'ajoute en tant qu'enfant au paragraphe.
Run run = new Run(doc);
run.Text = "Hello World!";
run.Font.Color = Color.Red;
para.AppendChild(run);

Assert.AreEqual("Hello World!", doc.GetText().Trim());

doc.Save(ArtifactsDir + "Section.CreateManually.docx");
```

### Voir également

* class [Run](../)
* espace de noms [Aspose.Words](../../run/)
* Assemblée [Aspose.Words](../../../)


