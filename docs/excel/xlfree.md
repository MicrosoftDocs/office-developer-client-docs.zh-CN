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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 2dd61ee5cd0e2e671cc47425689287b8a437732f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773853"
---
# <a name="xlfree"></a>xlFree

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
使用以释放内存资源分配由 Microsoft Excel 时创建返回值**XLOPER**/ **XLOPER12** [Excel4](excel4-excel12.md)、 [Excel4v](excel4v-excel12v.md)、 [Excel12](excel4-excel12.md)或[Excel12v](excel4v-excel12v.md)将调用。 **XlFree**函数释放的辅助内存和将指针重置为**空**，但不会销毁**XLOPER**其他部件/ **XLOPER12**。
  
```cs
Excel4(xlFree, 0, n, LPXLOPER px_1, ..., LPXLOPER px_n);
Excel12(xlFree, 0, n, LPXLOPER12 px_1, ..., LPXLOPER12 px_n);
```

## <a name="parameters"></a>参数

 _px_1，...px_n_
  
一个或多个**XLOPER**/ **XLOPER12**s 要释放。 在 Excel 版本中最多为 2003年，可以传递的指针的最大数量为 30。 从 Excel 2007 开始，这被增加到 255。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数不返回值。
  
## <a name="remarks"></a>备注

您必须释放返回值从**Excel4**或**Excel4v**获取每个**XLOPER**和返回值将从**Excel12**或获得**Excel12v**如果下列类型之一的每个**XLOPER12** : **xltypeStr**， **xltypeMulti**或**xltypeRef**。 始终是安全忙其他类型，即使它们不使用辅助内存，只要从**Excel4**或**Excel12**处获得。
  
其中您返回到 Excel 指向**XLOPER**/ **XLOPER12**仍包含 Excel 分配内存要释放，必须设置**xlbitXLFree**以确保内存的 Excel 版本。 
  
## <a name="example"></a>示例

此示例调用**获取。WORKSPACE(1)** 返回哪些 Excel 当前正在运行字符串形式的平台。 代码将复制此返回到供以后使用缓冲区的字符串。 该代码将缓冲区放回**XLOPER12**更高版本用于 Excel 函数。 最后，代码在警告框中显示的字符串。 
  
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

