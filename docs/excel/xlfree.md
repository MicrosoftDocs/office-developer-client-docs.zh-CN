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
  
用于在[Excel4](excel4-excel12.md)、 [Excel4v](excel4v-excel12v.md)、 [Excel12](excel4-excel12.md)或[Excel12v](excel4v-excel12v.md)的调用中创建返回值**XLOPER**/ **XLOPER12**时, 释放 Microsoft Excel 分配的内存资源。 **xlFree**函数释放辅助内存, 并将指针重置为**NULL** , 但不会销毁**XLOPER**/ **XLOPER12**的其他部分。
  
```cs
Excel4(xlFree, 0, n, LPXLOPER px_1, ..., LPXLOPER px_n);
Excel12(xlFree, 0, n, LPXLOPER12 px_1, ..., LPXLOPER12 px_n);
```

## <a name="parameters"></a>参数

 _px_1, ..., px_n_
  
一个或多个要释放的**XLOPER**/ **XLOPER12**s。 在 Excel 版本中, 最多为2003个, 可以传递的最大指针数为30个。 从 Excel 2007 开始, 这会增加到255。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数不返回值。
  
## <a name="remarks"></a>说明

您必须释放作为返回值从**Excel4**或**Excel4v**中获取的每个**XLOPER** , 以及从**Excel12**或**Excel12v**获取为返回值的每个**XLOPER12** , 如果它们是以下类型之一: **xltypeStr**、 **xltypeMulti**或**xltypeRef**。 即使您从**Excel4**或**Excel12**中获取了这些类型, 也始终可以安全地释放其他类型, 即使它们不使用辅助内存也是如此。
  
若要返回到 excel 的指针指向的**XLOPER**/ **XLOPER12**仍包含要释放的 Excel 分配内存, 则必须设置**xlbitXLFree**以确保 excel 释放内存。 
  
## <a name="example"></a>示例

此示例调用**GET。工作区 (1)** 以返回 Excel 当前以字符串形式运行的平台。 代码将返回的字符串复制到缓冲区中, 以供将来使用。 该代码将缓冲区放回**XLOPER12**中, 以供以后用于 Excel 函数。 最后, 代码在警告框中显示字符串。 
  
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

