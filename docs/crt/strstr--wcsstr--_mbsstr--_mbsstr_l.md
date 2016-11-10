---
title: "strstr, wcsstr, _mbsstr, _mbsstr_l"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_mbsstr"
  - "wcsstr"
  - "_mbsstr_l"
  - "strstr"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_fstrstr"
  - "_ftcsstr"
  - "strstr"
  - "wcsstr"
  - "_mbsstr"
  - "_tcsstr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "strings [C++], searching"
  - "mbsstr function"
  - "_ftcsstr function"
  - "ftcsstr function"
  - "fstrstr function"
  - "_tcsstr function"
  - "substrings, finding"
  - "mbsstr_l function"
  - "tcsstr function"
  - "_mbsstr function"
  - "wcsstr function"
  - "_fstrstr function"
  - "_mbsstr_l function"
  - "strstr function"
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
caps.latest.revision: 30
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
# strstr, wcsstr, _mbsstr, _mbsstr_l
Returns a pointer to the first occurrence of a search string in a string.  
  
> [!IMPORTANT]
>  `_mbsstr` and `_mbsstr_l` cannot be used in applications that execute in the [!INCLUDE[wrt](../atl/includes/wrt_md.md)]. For more information, see [CRT functions not supported with /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *strstr(  
   const char *str,  
   const char *strSearch   
); // C only  
char *strstr(  
   char *str,  
   const char *strSearch   
); // C++ only  
const char *strstr(  
   const char *str,  
   const char *strSearch   
); // C++ only  
wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C only  
wchar_t *wcsstr(  
   wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
const wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C only  
unsigned char *_mbsstr(  
   unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
const unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C only  
unsigned char *_mbsstr_l(  
   unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameters  
 `str`  
 Null-terminated string to search.  
  
 `strSearch`  
 Null-terminated string to search for.  
  
 `locale`  
 Locale to use.  
  
## Return Value  
 Returns a pointer to the first occurrence of `strSearch` in `str`, or `NULL` if `strSearch` does not appear in `str`. If `strSearch` points to a string of zero length, the function returns `str`.  
  
## Remarks  
 The `strstr` function returns a pointer to the first occurrence of `strSearch` in `str`. The search does not include terminating null characters. `wcsstr` is the wide-character version of `strstr` and `_mbsstr` is the multibyte-character version. The arguments and return value of `wcsstr` are wide-character strings; those of `_mbsstr` are multibyte-character strings. `_mbsstr` validates its parameters. If `str` or `strSearch` is `NULL`, the invalid parameter handler is invoked, as described in [Parameter Validation](../crt/parameter-validation.md) . If execution is allowed to continue, `_mbsstr` sets `errno` to `EINVAL` and returns 0. `strstr` and `wcsstr` do not validate their parameters. These three functions behave identically otherwise.  
  
> [!IMPORTANT]
>  These functions might incur a threat from a buffer overrun problem. Buffer overrun problems can be used to attack a system because they can allow the execution of arbitrary code, which can cause an unwarranted elevation of privilege. For more information, see [Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 In C, these functions take a `const` pointer for the first argument. In C++, two overloads are available. The overload that takes a pointer to `const` returns a pointer to `const`; the version that takes a pointer to non-`const` returns a pointer to non-`const`. The macro _CONST_CORRECT_OVERLOADS is defined if both the `const` and non-`const` versions of these functions are available. If you require the non-`const` behavior for both C++ overloads, define the symbol _CONST_RETURN.  
  
 The output value is affected by the locale-category setting of `LC_CTYPE`; for more information, see [setlocale, _wsetlocale](../crt/setlocale--_wsetlocale.md). The versions of these functions that do not have the `_l` suffix use the current locale for this locale-dependent behavior; the versions that have the `_l` suffix are identical except that they instead use the locale parameter that's passed in. For more information, see [Locale](../crt/locale.md).  
  
### Generic-Text Routine Mappings  
  
|TCHAR.H routine|_UNICODE & _MBCS not defined|_MBCS defined|_UNICODE defined|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|  
|**n/a**|**n/a**|`_mbsstr_l`|**n/a**|  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`strstr`|\<string.h>|  
|`wcsstr`|\<string.h> or \<wchar.h>|  
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|  
  
 For more information about compatibility, see [Compatibility](../crt/compatibility.md).  
  
## Example  
  
```  
  
      // crt_strstr.c  
  
#include <string.h>  
#include <stdio.h>  
  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int  result;  
   printf( "String to be searched:\n   %s\n", string );  
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );  
   pdest = strstr( string, str );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "%s found at position %d\n", str, result );  
   else  
      printf( "%s not found\n", str );  
}  
```  
  
 **String to be searched:**  
 **The quick brown dog jumps over the lazy fox**  
 **1         2         3         4         5**  
 **12345678901234567890123456789012345678901234567890**  
**lazy found at position 36**   
## .NET Framework Equivalent  
 [System::String::IndexOf](https://msdn.microsoft.com/en-us/library/system.string.indexof.aspx)  
  
## See Also  
 [String Manipulation](../crt/string-manipulation--crt-.md)   
 [Locale](../crt/locale.md)   
 [Interpretation of Multibyte-Character Sequences](../crt/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../crt/strcspn--wcscspn--_mbscspn--_mbscspn_l.md)   
 [strcmp, wcscmp, _mbscmp](../crt/strcmp--wcscmp--_mbscmp.md)   
 [strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](../crt/strpbrk--wcspbrk--_mbspbrk--_mbspbrk_l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../crt/strrchr--wcsrchr--_mbsrchr--_mbsrchr_l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../crt/strspn--wcsspn--_mbsspn--_mbsspn_l.md)   
 [basic_string::find](../Topic/basic_string::find.md)