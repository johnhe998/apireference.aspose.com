---
title: FieldArgumentBuilder.AddNode
second_title: Aspose.Words för .NET API Referens
description: FieldArgumentBuilder metod. Lägger till en nod till argumentet.
type: docs
weight: 30
url: /sv/net/aspose.words.fields/fieldargumentbuilder/addnode/
---
## FieldArgumentBuilder.AddNode method

Lägger till en nod till argumentet.

```csharp
public FieldArgumentBuilder AddNode(Inline node)
```

### Anmärkningar

Endast textnivånoder stöds för tillfället.

### Exempel

Visar hur man konstruerar fält med en fältbyggare och sedan infogar dem i dokumentet.

```csharp
Document doc = new Document();

// Nedan är tre exempel på fältkonstruktioner gjorda med en fältbyggare.
// 1 - Enstaka fält:
// Använd en fältbyggare för att lägga till ett SYMBOLfält som visar symbolen ƒ (Florin).
FieldBuilder builder = new FieldBuilder(FieldType.FieldSymbol);
builder.AddArgument(402);
builder.AddSwitch("\\f", "Arial");
builder.AddSwitch("\\s", 25);
builder.AddSwitch("\\u");
Field field = builder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);

Assert.AreEqual(" SYMBOL 402 \\f Arial \\s 25 \\u ", field.GetFieldCode());

// 2 - Kapslade fält:
// Använd en fältbyggare för att skapa ett formelfält som används som ett inre fält av en annan fältbyggare.
FieldBuilder innerFormulaBuilder = new FieldBuilder(FieldType.FieldFormula);
innerFormulaBuilder.AddArgument(100);
innerFormulaBuilder.AddArgument("+");
innerFormulaBuilder.AddArgument(74);

// Skapa ytterligare en byggare för ett annat SYMBOL-fält och infoga formelfältet
 // som vi har skapat ovan i SYMBOL-fältet som dess argument.
builder = new FieldBuilder(FieldType.FieldSymbol);
builder.AddArgument(innerFormulaBuilder);
field = builder.BuildAndInsert(doc.FirstSection.Body.AppendParagraph(string.Empty));

// Det yttre SYMBOL-fältet kommer att använda formelfältsresultatet, 174, som sitt argument,
// som gör att fältet visar symbolen ® (Registered Sign) eftersom dess teckennummer är 174.
Assert.AreEqual(" SYMBOL \u0013 = 100 + 74 \u0014\u0015 ", field.GetFieldCode());

// 3 - Flera kapslade fält och argument:
// Nu kommer vi att använda en byggare för att skapa ett IF-fält, som visar ett av två anpassade strängvärden,
// beroende på värdet sant/falskt för dess uttryck. För att få ett sant/falskt värde
// som bestämmer vilken sträng IF-fältet visar, kommer IF-fältet att testa två numeriska uttryck för likhet.
// Vi kommer att tillhandahålla de två uttrycken i form av formelfält, som vi kapslar inuti IF-fältet.
FieldBuilder leftExpression = new FieldBuilder(FieldType.FieldFormula);
leftExpression.AddArgument(2);
leftExpression.AddArgument("+");
leftExpression.AddArgument(3);

FieldBuilder rightExpression = new FieldBuilder(FieldType.FieldFormula);
rightExpression.AddArgument(2.5);
rightExpression.AddArgument("*");
rightExpression.AddArgument(5.2);

// Därefter kommer vi att bygga två fältargument, som kommer att fungera som sanna/falska utdatasträngar för IF-fältet.
// Dessa argument kommer att återanvända utdatavärdena för våra numeriska uttryck.
FieldArgumentBuilder trueOutput = new FieldArgumentBuilder();
trueOutput.AddText("True, both expressions amount to ");
trueOutput.AddField(leftExpression);

FieldArgumentBuilder falseOutput = new FieldArgumentBuilder();
falseOutput.AddNode(new Run(doc, "False, "));
falseOutput.AddField(leftExpression);
falseOutput.AddNode(new Run(doc, " does not equal "));
falseOutput.AddField(rightExpression);

  // Slutligen kommer vi att skapa ytterligare en fältbyggare för IF-fältet och kombinera alla uttryck.
builder = new FieldBuilder(FieldType.FieldIf);
builder.AddArgument(leftExpression);
builder.AddArgument("=");
builder.AddArgument(rightExpression);
builder.AddArgument(trueOutput);
builder.AddArgument(falseOutput);
field = builder.BuildAndInsert(doc.FirstSection.Body.AppendParagraph(string.Empty));

Assert.AreEqual(" IF \u0013 = 2 + 3 \u0014\u0015 = \u0013 = 2.5 * 5.2 \u0014\u0015 " +
                "\"True, both expressions amount to \u0013 = 2 + 3 \u0014\u0015\" " +
                "\"False, \u0013 = 2 + 3 \u0014\u0015 does not equal \u0013 = 2.5 * 5.2 \u0014\u0015\" ", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.SYMBOL.docx");
```

### Se även

* class [Inline](../../../aspose.words/inline/)
* class [FieldArgumentBuilder](../)
* namnutrymme [Aspose.Words.Fields](../../fieldargumentbuilder/)
* hopsättning [Aspose.Words](../../../)


