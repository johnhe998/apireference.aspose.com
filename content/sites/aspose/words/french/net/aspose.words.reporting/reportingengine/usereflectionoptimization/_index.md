---
title: ReportingEngine.UseReflectionOptimization
second_title: Référence de l'API Aspose.Words pour .NET
description: ReportingEngine propriété. Obtient ou définit une valeur indiquant si les appels de membres de type personnalisé effectués via lAPI de réflexion sont optimisés à laide de la génération de classe dynamique ou non. La valeur par défaut est true.
type: docs
weight: 70
url: /fr/net/aspose.words.reporting/reportingengine/usereflectionoptimization/
---
## ReportingEngine.UseReflectionOptimization property

Obtient ou définit une valeur indiquant si les appels de membres de type personnalisé effectués via l'API de réflexion sont optimisés à l'aide de la génération de classe dynamique ou non. La valeur par défaut est true.

```csharp
public static bool UseReflectionOptimization { get; set; }
```

### Remarques

Il existe certains scénarios où il est préférable de désactiver cette optimisation. Par exemple, si vous traitez avec de petites collections d'éléments de données tout le temps, une surcharge de génération de classe dynamique peut être plus perceptible qu'une surcharge d'appels d'API de réflexion directe. L'option n'a pas d'effet lorsqu'elle est exécutée sur L'optimisation d'iOS et de réflexion n'est pas utilisée.

### Voir également

* class [ReportingEngine](../)
* espace de noms [Aspose.Words.Reporting](../../reportingengine/)
* Assemblée [Aspose.Words](../../../)


