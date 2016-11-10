---
title: "Compiler Error CS1016"
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
  - "CS1016"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1016"
ms.assetid: 576e6e12-981c-43b6-9e4a-29fa4e9f76e8
caps.latest.revision: 7
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
# Compiler Error CS1016
Named attribute argument expected  
  
 Unnamed attribute arguments must appear before the named arguments.  
  
## Example  
 The following sample generates CS1016:  
  
```  
// CS1016.cs  
using System;  
  
[AttributeUsage(AttributeTargets.Class)]  
public class HelpAttribute : Attribute  
{  
    public HelpAttribute(string url)   // url is a positional parameter  
    {  
        m_url = url;  
    }  
  
    public string Topic = null;      // Topic is a named parameter  
    private string m_url = null;  
}  
  
[HelpAttribute(Topic="Samples", "http://intranet/inhouse")]   // CS1016  
// try the following line instead  
//[HelpAttribute("http://intranet/inhouse", Topic="Samples")]  
public class MainClass  
{  
    public static void Main ()  
    {  
    }  
}  
```