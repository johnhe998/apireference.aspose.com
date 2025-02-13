---
title: Style.BuiltIn
second_title: Aspose.Words für .NET-API-Referenz
description: Style eigendom. Wahr wenn dieser Stil einer der integrierten Stile in MS Word ist.
type: docs
weight: 30
url: /de/net/aspose.words/style/builtin/
---
## Style.BuiltIn property

Wahr, wenn dieser Stil einer der integrierten Stile in MS Word ist.

```csharp
public bool BuiltIn { get; }
```

### Beispiele

Zeigt, wie benutzerdefinierte Stile von integrierten Stilen unterschieden werden.

```csharp
Document doc = new Document();

// Wenn wir ein Dokument mit Microsoft Word oder programmgesteuert mit Aspose.Words erstellen,
// Das Dokument enthält eine Sammlung von Stilen, die auf seinen Text angewendet werden können, um sein Erscheinungsbild zu ändern.
// Wir können auf diese eingebauten Stile über die "Styles"-Sammlung des Dokuments zugreifen.
// Bei diesen Stilen ist das Flag "BuiltIn" auf "true" gesetzt.
Style style = doc.Styles["Emphasis"];

Assert.True(style.BuiltIn);

// Erstellen Sie einen benutzerdefinierten Stil und fügen Sie ihn der Sammlung hinzu.
 // Bei benutzerdefinierten Stilen wie diesem wird das "BuiltIn"-Flag auf "false" gesetzt.
style = doc.Styles.Add(StyleType.Character, "MyStyle");
style.Font.Color = Color.Navy;
style.Font.Name = "Courier New";

Assert.False(style.BuiltIn);
```

### Siehe auch

* class [Style](../)
* namensraum [Aspose.Words](../../style/)
* Montage [Aspose.Words](../../../)


