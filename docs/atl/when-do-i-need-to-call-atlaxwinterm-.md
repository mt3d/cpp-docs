---
title: "When Do I Need to Call AtlAxWinTerm?"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "AtlAxWinTerm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlAxWinTerm method"
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: 9
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
# When Do I Need to Call AtlAxWinTerm?
[AtlAxWinTerm](../Topic/AtlAxWinTerm.md) unregisters the **"AtlAxWin80"** window class. You should call this function (if you no longer need to create host windows) after all existing host windows have been destroyed. If you don't call this function, the window class will be unregistered automatically when the process terminates.  
  
## See Also  
 [When Do I Need to Call AtlAxWinInit?](../atl/when-do-i-need-to-call-atlaxwininit-.md)   
 [Control Containment FAQ](../atl/atl-control-containment-faq.md)