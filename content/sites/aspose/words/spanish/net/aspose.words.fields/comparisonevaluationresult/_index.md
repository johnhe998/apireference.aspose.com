---
title: Class ComparisonEvaluationResult
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fields.ComparisonEvaluationResult clase. El resultado de la evaluación de comparación.
type: docs
weight: 1330
url: /es/net/aspose.words.fields/comparisonevaluationresult/
---
## ComparisonEvaluationResult class

El resultado de la evaluación de comparación.

```csharp
public sealed class ComparisonEvaluationResult
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [ComparisonEvaluationResult](comparisonevaluationresult/#constructor)(bool) | Crea un resultado de evaluación de comparación. |
| [ComparisonEvaluationResult](comparisonevaluationresult/#constructor_1)(string) | Crea un resultado de evaluación de comparación fallido con el mensaje de error correspondiente. |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [ErrorMessage](../../aspose.words.fields/comparisonevaluationresult/errormessage/) { get; } | Obtiene el mensaje de error del resultado de la evaluación de comparación fallida. |
| [Result](../../aspose.words.fields/comparisonevaluationresult/result/) { get; } | Obtiene el resultado de la evaluación de la comparación. |

### Ejemplos

Muestra cómo implementar una evaluación personalizada para los campos IF y COMPARE.

```csharp
public void ConditionEvaluationExtensionPoint(string fieldCode, sbyte comparisonResult, string comparisonError,
    string expectedResult)
{
    const string left = "\"left expression\"";
    const string @operator = "<>";
    const string right = "\"right expression\"";

    DocumentBuilder builder = new DocumentBuilder();

    // Códigos de campo que usamos en este ejemplo:
    // 1. " IF {0} {1} {2} \"argumento verdadero\" \"argumento falso\" ".
    // 2. " COMPARAR {0} {1} {2} ".
    Field field = builder.InsertField(string.Format(fieldCode, left, @operator, right), null);

    // Si el "Resultado de comparación" no está definido, creamos "Resultado de evaluación de comparación" con una cadena, en lugar de bool.
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
/// Evaluación de expresiones de comparación para FieldIf y FieldCompare.
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

### Ver también

* espacio de nombres [Aspose.Words.Fields](../../aspose.words.fields/)
* asamblea [Aspose.Words](../../)


