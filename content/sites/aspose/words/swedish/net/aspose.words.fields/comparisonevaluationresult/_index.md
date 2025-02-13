---
title: Class ComparisonEvaluationResult
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Fields.ComparisonEvaluationResult klass. Resultatet av jämförelseutvärderingen.
type: docs
weight: 1330
url: /sv/net/aspose.words.fields/comparisonevaluationresult/
---
## ComparisonEvaluationResult class

Resultatet av jämförelseutvärderingen.

```csharp
public sealed class ComparisonEvaluationResult
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [ComparisonEvaluationResult](comparisonevaluationresult/#constructor)(bool) | Skapar ett resultat för jämförelseutvärdering. |
| [ComparisonEvaluationResult](comparisonevaluationresult/#constructor_1)(string) | Skapar ett misslyckat resultat för jämförelseutvärdering med motsvarande felmeddelande. |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [ErrorMessage](../../aspose.words.fields/comparisonevaluationresult/errormessage/) { get; } | Får felmeddelandet om resultatet av den misslyckade jämförelseutvärderingen. |
| [Result](../../aspose.words.fields/comparisonevaluationresult/result/) { get; } | Får resultatet av jämförelseutvärderingen. |

### Exempel

Visar hur man implementerar anpassad utvärdering för IF- och COMPARE-fälten.

```csharp
public void ConditionEvaluationExtensionPoint(string fieldCode, sbyte comparisonResult, string comparisonError,
    string expectedResult)
{
    const string left = "\"left expression\"";
    const string @operator = "<>";
    const string right = "\"right expression\"";

    DocumentBuilder builder = new DocumentBuilder();

    // Fältkoder som vi använder i detta exempel:
    // 1. " IF {0} {1} {2} \"true argument\" \"false argument\" ".
    // 2. " JÄMFÖR {0} {1} {2} ".
    Field field = builder.InsertField(string.Format(fieldCode, left, @operator, right), null);

    // Om "comparisonResult" är odefinierat skapar vi "ComparisonEvaluationResult" med sträng, istället för bool.
    ComparisonEvaluationResult result = comparisonResult != -1
        ? new ComparisonEvaluationResult(comparisonResult == 1)
        : comparisonError != null ? new ComparisonEvaluationResult(comparisonError) : null;

    ComparisonExpressionEvaluator evaluator = new ComparisonExpressionEvaluator(result);
    builder.Document.FieldOptions.ComparisonExpressionEvaluator = evaluator;

    builder.Document.UpdateFields();

    Assert.AreEqual(expectedResult, field.Result);
    evaluator.AssertInvocationsCount(1).AssertInvocationArguments(0, left, @operator, right);
}

/// <summary>
/// Utvärdering av jämförelseuttryck för FieldIf och FieldCompare.
/// </summary>
private class ComparisonExpressionEvaluator : IComparisonExpressionEvaluator
{
    public ComparisonExpressionEvaluator(ComparisonEvaluationResult result)
    {
        mResult = result;
    }

    public ComparisonEvaluationResult Evaluate(Field field, ComparisonExpression expression)
    {
        mInvocations.Add(new[]
        {
            expression.LeftExpression,
            expression.ComparisonOperator,
            expression.RightExpression
        });

        return mResult;
    }

    public ComparisonExpressionEvaluator AssertInvocationsCount(int expected)
    {
        Assert.AreEqual(expected, mInvocations.Count);
        return this;
    }

    public ComparisonExpressionEvaluator AssertInvocationArguments(
        int invocationIndex,
        string expectedLeftExpression,
        string expectedComparisonOperator,
        string expectedRightExpression)
    {
        string[] arguments = mInvocations[invocationIndex];

        Assert.AreEqual(expectedLeftExpression, arguments[0]);
        Assert.AreEqual(expectedComparisonOperator, arguments[1]);
        Assert.AreEqual(expectedRightExpression, arguments[2]);

        return this;
    }

    private readonly ComparisonEvaluationResult mResult;
    private readonly List<string[]> mInvocations = new List<string[]>();
}
```

### Se även

* namnutrymme [Aspose.Words.Fields](../../aspose.words.fields/)
* hopsättning [Aspose.Words](../../)


