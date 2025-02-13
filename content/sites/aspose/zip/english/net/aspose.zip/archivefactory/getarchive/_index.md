---
title: GetArchive
second_title: Aspose.ZIP for .NET API Reference
description: 
type: docs
weight: 10
url: /net/aspose.zip/archivefactory/getarchive/
---
## ArchiveFactory.GetArchive method (1 of 2)

Detects the archive format and creates the appropriate [`IArchive`](../../iarchive) object according to the type of archive specified by the given path.

```csharp
public static IArchive GetArchive(string path)
```

| Parameter | Type | Description |
| --- | --- | --- |
| path | String | The path to the archive to be analyzed. |

### Return Value

An [`IArchive`](../../iarchive) object representing the archive.

### See Also

* interface [IArchive](../../iarchive)
* class [ArchiveFactory](../../archivefactory)
* namespace [Aspose.Zip](../../archivefactory)
* assembly [Aspose.Zip](../../../)

---

## ArchiveFactory.GetArchive method (2 of 2)

Detects the archive format and creates the appropriate [`IArchive`](../../iarchive) object according to the type of archive specified by the given stream.

```csharp
public static IArchive GetArchive(Stream stream)
```

| Parameter | Type | Description |
| --- | --- | --- |
| stream | Stream | The stream containing the archive data. It must bee seekable. |

### Return Value

An [`IArchive`](../../iarchive) object representing the archive.

### See Also

* interface [IArchive](../../iarchive)
* class [ArchiveFactory](../../archivefactory)
* namespace [Aspose.Zip](../../archivefactory)
* assembly [Aspose.Zip](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.ZIP.dll -->
