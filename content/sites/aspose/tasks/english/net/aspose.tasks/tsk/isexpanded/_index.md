---
title: IsExpanded
second_title: Aspose.Tasks for .NET API Reference
description: Determines whether a summary task is expanded or not in GanttChart view.
type: docs
weight: 600
url: /net/aspose.tasks/tsk/isexpanded/
---
## Tsk.IsExpanded field

Determines whether a summary task is expanded or not in GanttChart view.

```csharp
public static readonly Key<NullableBool, TaskKey> IsExpanded;
```

### Examples

Shows how to read/write Tsk.IsExpanded property.

```csharp
var project = new Project();

var task = project.RootTask.Children.Add("Task");

task.Set(Tsk.IsExpanded, true);

Console.WriteLine("Is Expanded: " + task.Get(Tsk.IsExpanded));
```

### See Also

* struct [Key&lt;T,K&gt;](../../key-2)
* struct [NullableBool](../../nullablebool)
* enum [TaskKey](../../taskkey)
* class [Tsk](../../tsk)
* namespace [Aspose.Tasks](../../tsk)
* assembly [Aspose.Tasks](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Tasks.dll -->
