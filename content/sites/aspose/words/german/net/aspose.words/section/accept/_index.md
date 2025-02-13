---
title: Section.Accept
second_title: Aspose.Words für .NET-API-Referenz
description: Section methode. Akzeptiert einen Besucher.
type: docs
weight: 70
url: /de/net/aspose.words/section/accept/
---
## Section.Accept method

Akzeptiert einen Besucher.

```csharp
public override bool Accept(DocumentVisitor visitor)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| visitor | DocumentVisitor | Der Besucher, der die Knoten besucht. |

### Rückgabewert

True, wenn alle Knoten besucht wurden; false, wenn DocumentVisitor den Vorgang beendet hat, bevor alle Knoten besucht wurden.

### Bemerkungen

Listet diesen Knoten und alle seine untergeordneten Elemente auf. Jeder Knoten ruft eine entsprechende Methode auf DocumentVisitor auf.

Weitere Informationen finden Sie im Besucher-Entwurfsmuster.

Ruft DocumentVisitor.VisitSectionStart auf, ruft dann Accept für alle untergeordneten Knoten des Abschnitts auf und ruft am Ende DocumentVisitor.VisitSectionEnd auf.

### Siehe auch

* class [DocumentVisitor](../../documentvisitor/)
* class [Section](../)
* namensraum [Aspose.Words](../../section/)
* Montage [Aspose.Words](../../../)


