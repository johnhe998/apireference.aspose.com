---
title: WebExtension.IsFrozen
second_title: Aspose.Words för .NET API Referens
description: WebExtension fast egendom. Anger om användaren kan interagera med webbtillägget eller inte.
type: docs
weight: 40
url: /sv/net/aspose.words.webextensions/webextension/isfrozen/
---
## WebExtension.IsFrozen property

Anger om användaren kan interagera med webbtillägget eller inte.

```csharp
public bool IsFrozen { get; set; }
```

### Exempel

Visar hur man lägger till ett webbtillägg till ett dokument.

```csharp
Document doc = new Document();

// Skapa aktivitetsfönster med "MyScript"-tillägget, som kommer att användas av dokumentet,
// ställ sedan in dess standardplats.
TaskPane myScriptTaskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(myScriptTaskPane);
myScriptTaskPane.DockState = TaskPaneDockState.Right;
myScriptTaskPane.IsVisible = true;
myScriptTaskPane.Width = 300;
myScriptTaskPane.IsLocked = true;

// Om det finns flera uppgiftsrutor på samma dockningsplats kan vi ställa in detta index för att ordna dem.
myScriptTaskPane.Row = 1;

// Skapa ett tillägg som heter "MyScript Math Sample", som aktivitetsfönstret kommer att visas i.
WebExtension webExtension = myScriptTaskPane.WebExtension;

// Ställ in referensparametrar för applikationsarkivet för vårt tillägg, till exempel ID.
webExtension.Reference.Id = "WA104380646";
webExtension.Reference.Version = "1.0.0.0";
webExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
webExtension.Reference.Store = CultureInfo.CurrentCulture.Name;
webExtension.Properties.Add(new WebExtensionProperty("MyScript", "MyScript Math Sample"));
webExtension.Bindings.Add(new WebExtensionBinding("MyScript", WebExtensionBindingType.Text, "104380646"));

// Tillåt användaren att interagera med tillägget.
webExtension.IsFrozen = false;

// Vi kan komma åt webbtillägget i Microsoft Word via utvecklare -> Tillägg.
doc.Save(ArtifactsDir + "Document.WebExtension.docx");

// Ta bort alla aktivitetsrutor för webbtillägg på en gång så här.
doc.WebExtensionTaskPanes.Clear();

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Se även

* class [WebExtension](../)
* namnutrymme [Aspose.Words.WebExtensions](../../webextension/)
* hopsättning [Aspose.Words](../../../)


