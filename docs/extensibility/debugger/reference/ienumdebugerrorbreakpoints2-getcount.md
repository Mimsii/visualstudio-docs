---
description: "Returns the number of elements in the error breakpoints enumeration."
title: IEnumDebugErrorBreakpoints2::GetCount
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugErrorBreakpoints2::GetCount
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2::GetCount
author: maiak
ms.author: maiak
manager: mijacobs
ms.subservice: debug-diagnostics
dev_langs:
- CPP
- CSharp
---
# IEnumDebugErrorBreakpoints2::GetCount

Returns the number of elements in the enumeration.

## Syntax

### [C#](#tab/csharp)
```csharp
int GetCount(
   out uint pcelt
);
```
### [C++](#tab/cpp)
```cpp
HRESULT GetCount(
   ULONG* pcelt
);
```
---

## Parameters
`pcelt`\
[out] Returns the number of elements in the enumeration.

## Return Value
 If successful, returns `S_OK`; otherwise, returns an error code.

## Remarks
 This method is not part of the customary COM enumeration interface which specifies that only the `Next`, `Clone`, `Skip`, and `Reset` methods need to be implemented.

## See also
- [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)
