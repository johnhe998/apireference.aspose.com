---
title: Bulleted List
linktitle: Bulleted List
second_title: Aspose.Words for .NET API Reference
description: Learn how to create a bulleted list with Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/working-with-markdown/bulleted-list/
---

In this tutorial, we are going to tell you how to create a bulleted list with Aspose.Words for .NET. A bulleted list is used to list items without using numbering.

## Step 1: Using a document generator

First, we'll use a document generator to add content to our document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Step 2: Applying a Default Bulleted List

We can apply a default bulleted list using the document builder's `ApplyBulletDefault` method.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Step 3: Customizing the Bullet Format

We can customize the bullet format by accessing the properties of `ListFormat.List.ListLevels[0]`. In this example, we use the dash "-" as a bullet.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Step 4: Adding items to the list

Now we can add items to the bulleted list using the document builder's `Writeln` method.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Step 5: Removing indentation from the list

If we want to create a sublist, we can increase the indentation using the `ListFormat.ListIndent()` method. In this example, we are adding a sublist to items 2a and 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Example source code for Bulleted List using Aspose.Words for .NET


```csharp
	// Use a document builder to add content to the document.
	DocumentBuilder builder = new DocumentBuilder();

	builder.ListFormat.ApplyBulletDefault();
	builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();

	builder.Writeln("Item 2a");
	builder.Writeln("Item 2b");
            
```

Congratulation ! You have now learned how to create a bulleted list with Aspose.Words for .NET.


