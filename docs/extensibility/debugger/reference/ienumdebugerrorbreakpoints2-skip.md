---
description: "Skips over the specified number of elements in the error breakpoint enumeration."
title: IEnumDebugErrorBreakpoints2::Skip
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugErrorBreakpoints2::Skip
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2::Skip
author: maiak
ms.author: maiak
manager: mijacobs
ms.subservice: debug-diagnostics
dev_langs:
- CPP
- CSharp
---
# IEnumDebugErrorBreakpoints2::Skip

Skips over the specified number of elements.

## Syntax

### [C#](#tab/csharp)
```csharp
int Skip(
   uint celt
);
```
### [C++](#tab/cpp)
```cpp
HRESULT Skip(
   ULONG celt
);
```
---

## Parameters
`celt`\
[in] Number of elements to skip.

## Return Value
 If successful, returns `S_OK`. Returns `S_FALSE` if `celt` is greater than the number of remaining elements; otherwise, returns an error code.

## Remarks
 If `celt` specifies a value greater than the number of remaining elements, the enumeration is set to the end and `S_FALSE` is returned.

## See also
- [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)
