---
title: RuleBasedLabeling.Add
second_title: Aspose.GIS for .NET API Reference
description: RuleBasedLabeling method. Adds new LabelingRule.
type: docs
weight: 40
url: /net/aspose.gis.rendering.labelings/rulebasedlabeling/add/
---
## Add(Func&lt;Feature, bool&gt;, Labeling) {#add_1}

Adds new [`LabelingRule`](../../labelingrule/).

```csharp
public void Add(Func<Feature, bool> filter, Labeling labeling)
```

| Parameter | Type | Description |
| --- | --- | --- |
| filter | Func`2 | Determines when labeling should be applied to a feature. |
| labeling | Labeling | Labeling to apply to a feature when *filter* returns true. |

### See Also

* class [Feature](../../../aspose.gis/feature/)
* class [Labeling](../../labeling/)
* class [RuleBasedLabeling](../)
* namespace [Aspose.Gis.Rendering.Labelings](../../rulebasedlabeling/)
* assembly [Aspose.GIS](../../../)

---

## Add(LabelingRule) {#add}

Adds a rule.

```csharp
public void Add(LabelingRule rule)
```

| Parameter | Type | Description |
| --- | --- | --- |
| rule | LabelingRule | Rule to add. |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Argument is `null`. |

### See Also

* class [LabelingRule](../../labelingrule/)
* class [RuleBasedLabeling](../)
* namespace [Aspose.Gis.Rendering.Labelings](../../rulebasedlabeling/)
* assembly [Aspose.GIS](../../../)


