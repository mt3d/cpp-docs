---
title: "Memory Management: Resizable Memory Blocks"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memory blocks, resizable"
  - "memory, corruption"
  - "memory allocation, memory block size"
  - "memory blocks, allocating"
  - "blocks, memory allocation"
  - "resizable memory blocks"
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
caps.latest.revision: 7
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Memory Management: Resizable Memory Blocks
The **new** and **delete** operators, described in the article [Memory Management: Examples](../mfc/memory-management--examples.md), are good for allocating and deallocating fixed-size memory blocks and objects. Occasionally, your application may need resizable memory blocks. You must use the standard C run-time library functions [malloc](../crt/malloc.md), [realloc](../crt/realloc.md), and [free](../crt/free.md) to manage resizable memory blocks on the heap.  
  
> [!IMPORTANT]
>  Mixing the **new** and **delete** operators with the resizable memory-allocation functions on the same memory block will result in corrupted memory in the Debug version of MFC. You should not use `realloc` on a memory block allocated with **new**. Likewise, you should not allocate a memory block with the **new** operator and delete it with **free**, or use the **delete** operator on a block of memory allocated with `malloc`.  
  
## See Also  
 [Memory Management: Heap Allocation](../mfc/memory-management--heap-allocation.md)