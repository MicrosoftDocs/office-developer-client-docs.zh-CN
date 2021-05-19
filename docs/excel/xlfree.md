---
title: xlFree
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlFree
keywords:
- xlfree 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 8ce2eef2-0138-495d-b6cb-bbb727a3cda4
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: de1c75ad65acacd44644e9bfb111b30abd0a578e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424712"
---
# <a name="xlfree"></a>xlFree

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用于在对 /  [Excel4、Excel4v、Excel12](excel4-excel12.md)或 [Excel12v](excel4v-excel12v.md)的调用中Microsoft Excel **XLOPER XLOPER12** [](excel4-excel12.md)创建返回值时，释放由 Microsoft Excel 分配的内存资源。 [](excel4v-excel12v.md) **xlFree** 函数释放辅助内存，将指针重置为 **NULL，** 但不销毁 **XLOPER** /  **XLOPER12** 的其他部分。
  
```cs
Excel4(xlFree, 0, n, LPXLOPER px_1, ..., LPXLOPER px_n);
Excel12(xlFree, 0, n, LPXLOPER12 px_1, ..., LPXLOPER12 px_n);
```

## <a name="parameters"></a>参数

 _px_1、...、px_n_
  
要释放的 **一** 个或多个 /  **XLOPER XLOPER12。** 在Excel 2003 版本中，可以传递的最大指针数为 30。 从 2007 Excel，增加到 255。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数不返回值。
  
## <a name="remarks"></a>备注

您必须释放从 **Excel4 或** **Excel4v** 获取的作为返回值获取的 **每个 XLOPER，** 以及从 Excel12 或 **Excel12v** 获取的作为返回值获取的每一 **个 XLOPER（** 如果它们是以下类型之一 **）：xltypeStr、xltypeMulti** 或 **xltypeRef**。   释放其他类型的内存始终安全，即使它们不使用辅助内存，只要从 **Excel4** 或 **Excel12** 获得它们。
  
如果返回到 Excel指向 **仍** 包含要释放的 Excel 分配的内存的 /  **XLOPER XLOPER12** 的指针，则必须设置 **xlbitXLFree** 以确保 Excel 释放内存。 
  
## <a name="example"></a>示例

此示例调用 **GET。WORKSPACE (1)** 返回当前作为字符串Excel运行平台。 代码将返回的字符串复制到缓冲区中，供以后使用。 该代码将缓冲区重新放入 **XLOPER12** 中，供以后与 Excel 函数一同使用。 最后，代码在警报框中显示字符串。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlFreeExample(void)
{
   XLOPER12 xRes, xInt;
   XCHAR buffer[cchMaxStz];
   int i,len;
   // Create an XLOPER12 for the argument to Getworkspace.
   xInt.xltype = xltypeInt;
   xInt.val.w = 1;
   // Call GetWorkspace.
   Excel12f(xlfGetWorkspace, &xRes, 1, (LPXLOPER12)&xInt);
   
   // Get the length of the returned string
   len = (int)xRes.val.str[0];
   //Take into account 1st char, which contains the length
   //and the null terminator. Truncate if necessary to fit
   //buffer.
   if (len > cchMaxStz - 2)
      len = cchMaxStz - 2;
   // Copy to buffer.
   for(i = 1; i <= len; i++)
      buffer[i] = xRes.val.str[i];
   // Null terminate, Not necessary but a good idea.
   buffer[len] = '\0';
   buffer[0] = len;
   // Free the string returned from Excel.
   Excel12f(xlFree, 0, 1, &xRes);
   // Create a new string XLOPER12 for the alert.
   xRes.xltype = xltypeStr;
   xRes.val.str = buffer;
   // Show the alert.
   Excel12f(xlcAlert, 0, 1, (LPXLOPER12)&xRes);
   return 1;
}
```

## <a name="see-also"></a>另请参阅

- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

