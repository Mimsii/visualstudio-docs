---
description: Retrieves the virtual address (VA) of the block.
title: "IDiaLineNumber::get_virtualAddress"
ms.date: "11/04/2016"
ms.topic: "reference"
dev_langs:
  - "C++"
helpviewer_keywords:
  - "IDiaLineNumber::get_virtualAddress method"
author: "mikejo5000"
ms.author: "mikejo"
manager: mijacobs
ms.subservice: debug-diagnostics
---

# IDiaLineNumber::get_virtualAddress

Retrieves the virtual address (VA) of the block.

## Syntax

```c++
HRESULT get_virtualAddress ( 
   ULONGLONG* pRetVal
);
```

#### Parameters

 `pRetVal`

[out] Returns the virtual address of the block.

## Return Value

If successful, returns `S_OK`. Returns `S_FALSE` if this property is not supported. Otherwise, returns an error code.

## See also

- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
