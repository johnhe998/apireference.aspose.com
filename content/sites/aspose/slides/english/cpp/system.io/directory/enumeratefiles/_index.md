---
title: EnumerateFiles()
second_title: Aspose.Slides for C++ API Reference
description: Searches for the files that satisfy the specified search criteria either in the specified directory or in the whole directory tree rooted in the specified directory.
type: docs
weight: 40
url: /cpp/system.io/directory/enumeratefiles/
---
## Directory::EnumerateFiles(const String\&, const String\&, SearchOption) method


Searches for the files that satisfy the specified search criteria either in the specified directory or in the whole directory tree rooted in the specified directory.

```cpp
static StringEnumerablePtr System::IO::Directory::EnumerateFiles(const String &path, const String &searchPattern=u"*", SearchOption searchOption=SearchOption::TopDirectoryOnly)
```


### Arguments

| Parameter | Type | Description |
| --- | --- | --- |
| path | const [String](../../../system/string/)\& | Full or relative path to the directory to search in |
| searchPattern | const [String](../../../system/string/)\& | The name pattern of the files to search for |
| searchOption | [SearchOption](../../searchoption/) | Specifies whether the search has to be performed in the specified directory only or in the whole directory tree rooted in the specified directory |

### Return Value

The enumerable collection of full paths of the found files whose names match **searchPattern**

## See Also

* Enum [SearchOption](../../searchoption/)
* Typedef [StringEnumerablePtr](../stringenumerableptr/)
* Class [String](../../../system/string/)
* Class [Directory](../)
* Namespace [System::IO](../../)
* Library [Aspose.Slides](../../../)