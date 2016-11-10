---
title: "Compiler Error CS0542"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0542"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0542"
ms.assetid: 68a89948-8b56-4cd5-95e2-0df7fcad50ac
caps.latest.revision: 9
ms.author: "billchi"
manager: "douge"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Compiler Error CS0542
'user-defined type' : member names cannot be the same as their enclosing type  
  
 The members of a class or struct cannot have the same name as the class or struct, unless the member is a constructor.  
  
 The following sample generates CS0542:  
  
```c#  
// CS0542.cs  
class C  
{  
    public int C;  
}  
```  
  
 This error might be caused if you inadvertently put a return type on a constructor, which in effect makes it into an ordinary method. The following example generates CS0542 because `F` is a method, not a constructor, because it has a return type:  
  
```c#  
// CS0542.cs  
class F  
{  
   // Remove void from F() to resolve the problem.  
   void F()   // CS0542, same name as the class  
   {  
   }  
}  
  
class MyClass  
{  
   public static void Main()  
   {  
   }  
}  
```  
  
 If your class is named 'Item' and has an indexer declared as `this`, you may get this error. A default indexer is given the name 'Item' in the emitted code, creating the conflict.  
  
```c#  
// CS0542b.cs  
class Item  
{  
   public int this[int i]  // CS0542  
   {  
      get  
      {  
         return 0;  
      }  
   }  
}  
  
class CMain  
{  
   public static void Main()  
   {  
   }  
}  
```