---
title: KnownTypeSet.Add
second_title: Aspose.Words för .NET API Referens
description: KnownTypeSet metod. Lägger till det angivnaType objekt till uppsättningen. KastarArgumentException in följande fall
type: docs
weight: 20
url: /sv/net/aspose.words.reporting/knowntypeset/add/
---
## KnownTypeSet.Add method

Lägger till det angivnaType objekt till uppsättningen. KastarArgumentException in följande fall:

-*type* är inget.

-*type* representerar en tomrumstyp.

-*type* representerar en osynlig typ, dvs en icke-public typ eller en offentlig kapslad typ som har en icke-public yttre typ.

-*type* representerar en generisk typ.

-*type* representerar en matristyp.

-*type* har redan lagts till i uppsättningen.

```csharp
public void Add(Type type)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| type | Type | AType objekt att lägga till. |

### Se även

* class [KnownTypeSet](../)
* namnutrymme [Aspose.Words.Reporting](../../knowntypeset/)
* hopsättning [Aspose.Words](../../../)


