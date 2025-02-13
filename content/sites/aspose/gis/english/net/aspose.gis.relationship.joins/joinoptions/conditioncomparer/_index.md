---
title: JoinOptions.ConditionComparer
second_title: Aspose.GIS for .NET API Reference
description: JoinOptions property. Defines the way the features of two layers are related in a query by specifying a logic to be used in comparing values from the features.
type: docs
weight: 20
url: /net/aspose.gis.relationship.joins/joinoptions/conditioncomparer/
---
## JoinOptions.ConditionComparer property

Defines the way the features of two layers are related in a query by specifying a logic to be used in comparing values from the features.

```csharp
public IEqualityComparer<object> ConditionComparer { get; set; }
```

### Remarks

By default, it determines if two objects are equal:

```csharp
EqualityComparer<object>.Default;  
```

### See Also

* class [JoinOptions](../)
* namespace [Aspose.Gis.Relationship.Joins](../../joinoptions/)
* assembly [Aspose.GIS](../../../)


