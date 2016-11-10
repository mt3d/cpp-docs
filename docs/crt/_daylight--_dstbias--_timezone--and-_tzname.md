---
title: "_daylight, _dstbias, _timezone, and _tzname"
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
  - "tzname"
  - "_timezone"
  - "timezone"
  - "_daylight"
  - "_tzname"
  - "daylight"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "time zones"
  - "time adjustments"
  - "timezone variables"
  - "_tzname function"
  - "_daylight function"
  - "_timezone function"
  - "daylight function"
  - "local time adjustments"
  - "timezone function"
  - "tzname function"
  - "time-zone variables"
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
caps.latest.revision: 12
ms.author: "corob"
manager: "ghogen"
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
# _daylight, _dstbias, _timezone, and _tzname
`_daylight`, `_dstbias`, `_timezone`, and `_tzname` are used in some time and date routines to make local-time adjustments. These global variables have been deprecated for the more secure functional versions, which should be used in place of the global variables.  
  
|Global variable|Functional equivalent|  
|---------------------|---------------------------|  
|`_daylight`|[_get_daylight](../crt/_get_daylight.md)|  
|`_dstbias`|[_get_dstbias](../crt/_get_dstbias.md)|  
|`_timezone`|[_get_timezone](../crt/_get_timezone.md)|  
|`_tzname`|[_get_tzname](../crt/_get_tzname.md)|  
  
 They are declared in Time.h as follows.  
  
## Syntax  
  
```  
extern int _daylight;   
extern int _dstbias;   
extern long _timezone;   
extern char *_tzname[2];  
```  
  
## Remarks  
 On a call to `_ftime`, `localtime`, or `_tzset`, the values of `_daylight`, `_dstbias`, `_timezone`, and `_tzname` are determined from the value of the `TZ` environment variable. If you do not explicitly set the value of `TZ`, `_tzname[0]` and `_tzname[1]` contain the default settings of "PST" and "PDT" respectively.  The time-manipulation functions ([_tzset](../crt/_tzset.md), [_ftime](../crt/_ftime--_ftime32--_ftime64.md), and [localtime](../crt/localtime--_localtime32--_localtime64.md)) attempt to set the values of `_daylight`, `_dstbias` and `_timezone` by querying the operating system for the default value of each variable. The time-zone global variable values are shown in the following table.  
  
|Variable|Value|  
|--------------|-----------|  
|`_daylight`|Nonzero if daylight saving time (DST) zone is specified in `TZ` or determined from the operating system; otherwise, 0. The default value is 1.|  
|`_dstbias`|Offset for daylight saving time.|  
|`_timezone`|Difference in seconds between coordinated universal time and local time. The default value is 28,800.|  
|`_tzname[0]`|Time-zone name derived from the `TZ` environment variable. The default value is "PST".|  
|`_tzname[1]`|DST zone name derived from the `TZ` environment variable. The default value is "PDT" (Pacific daylight time).|  
  
## See Also  
 [Global Variables](../crt/global-variables.md)   
 [_get_daylight](../crt/_get_daylight.md)   
 [_get_dstbias](../crt/_get_dstbias.md)   
 [_get_timezone](../crt/_get_timezone.md)   
 [_get_tzname](../crt/_get_tzname.md)