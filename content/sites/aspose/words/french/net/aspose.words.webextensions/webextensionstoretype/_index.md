---
title: Enum WebExtensionStoreType
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.WebExtensions.WebExtensionStoreType énumération. Énumère les types disponibles dun magasin dextensions Web.
type: docs
weight: 6510
url: /fr/net/aspose.words.webextensions/webextensionstoretype/
---
## WebExtensionStoreType enumeration

Énumère les types disponibles d'un magasin d'extensions Web.

```csharp
public enum WebExtensionStoreType
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| SPCatalog | `0` | Spécifie que le type de magasin est le catalogue d'entreprise SharePoint. |
| OMEX | `1` | Spécifie que le type de magasin est Office.com. |
| SPApp | `2` | Spécifie que le type de magasin est une application Web SharePoint. |
| Exchange | `3` | Spécifie que le type de magasin est un serveur Exchange. |
| FileSystem | `4` | Spécifie que le type de magasin est un partage de système de fichiers. |
| Registry | `5` | Spécifie que le type de magasin est le registre système. |
| ExCatalog | `6` | Spécifie que le type de magasin est Déploiement centralisé via Exchange. |
| Default | `0` | Valeur par défaut. |

### Exemples

Montre comment ajouter une extension Web à un document.

```csharp
Document doc = new Document();

// Créer un volet des tâches avec le complément "MyScript", qui sera utilisé par le document,
// puis définit son emplacement par défaut.
TaskPane myScriptTaskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(myScriptTaskPane);
myScriptTaskPane.DockState = TaskPaneDockState.Right;
myScriptTaskPane.IsVisible = true;
myScriptTaskPane.Width = 300;
myScriptTaskPane.IsLocked = true;

// S'il y a plusieurs volets de tâches dans le même emplacement d'ancrage, nous pouvons définir cet index pour les organiser.
myScriptTaskPane.Row = 1;

// Créez un complément appelé "MyScript Math Sample", dans lequel le volet des tâches s'affichera.
WebExtension webExtension = myScriptTaskPane.WebExtension;

// Définir les paramètres de référence du magasin d'applications pour notre complément, tels que l'ID.
webExtension.Reference.Id = "WA104380646";
webExtension.Reference.Version = "1.0.0.0";
webExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
webExtension.Reference.Store = CultureInfo.CurrentCulture.Name;
webExtension.Properties.Add(new WebExtensionProperty("MyScript", "MyScript Math Sample"));
webExtension.Bindings.Add(new WebExtensionBinding("MyScript", WebExtensionBindingType.Text, "104380646"));

// Autoriser l'utilisateur à interagir avec le complément.
webExtension.IsFrozen = false;

// Nous pouvons accéder à l'extension Web dans Microsoft Word via Developer -> Compléments.
doc.Save(ArtifactsDir + "Document.WebExtension.docx");

// Supprimer tous les volets de tâches d'extension Web à la fois comme ceci.
doc.WebExtensionTaskPanes.Clear();

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Voir également

* espace de noms [Aspose.Words.WebExtensions](../../aspose.words.webextensions/)
* Assemblée [Aspose.Words](../../)


