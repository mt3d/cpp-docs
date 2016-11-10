---
title: "Building External Projects"
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
  - "external projects"
  - "Visual C++ projects, external projects"
  - "builds [C++], external projects"
  - "projects [C++], external projects"
  - "Makefile projects, external projects"
ms.assetid: 650b7803-ea91-489d-bee3-8f3e990e223c
caps.latest.revision: 6
ms.author: "corob"
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
# Building External Projects
An external project is a Visual C++ project that uses a makefile or other facilities that are outside (foreign or external to) the Visual C++ development environment.  
  
 If you have an external project (for example, a makefile project) that you want to build in the Visual C++ development environment, create a Makefile project and specify your project's build command and output in the Makefile Application Wizard. For more information, see [Creating a Makefile Project](../ide/creating-a-makefile-project.md).  
  
 Note that Visual C++ no longer supports the ability to export a makefile for the active project from the development environment. Use [Devenv Command Line Switches](../Topic/Devenv%20Command%20Line%20Switches.md) to build Visual Studio projects at the command line.  
  
## See Also  
 [Building C++ Projects in Visual Studio](../ide/building-c---projects-in-visual-studio.md)