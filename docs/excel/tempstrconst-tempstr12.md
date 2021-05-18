---
title: TempStrConst/TempStr12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempStr12
- TempStrConst
keywords:
- tempstr12 函数 [excel 2007]，TempStrConst 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: faf4ee4e-8d33-4cb3-ae16-5648a837ee4f
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d93f9de021c7ba325d9c11af2cede0245ffbbf6b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407149"
---
# <a name="tempstrconsttempstr12"></a>TempStrConst/TempStr12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
创建包含 **xltypeStr** 字符串的临时 **XLOPER/XLOPER12** 的框架库函数，以以 null 结尾的源字符串作为输入。 函数分配新的内存缓冲区，将传入的字符串复制到该缓冲区中。 输入字符串不会更改，因此声明为 **const**。
  
```cs
LPXLOPER TempStrConst(const LPSTR str);
LPXLOPER12 TempStr12(const XCHAR* lpstr);
```

## <a name="parameters"></a>参数

 _str_
  
指向以 null 结尾的源字符串的指针。 对于 **XLOPER，TempStrConst** 将截断长度超过 255 字节的字符串。 对于 **XLOPER12，TempStr12Const** 将截断长度超过 32，767 Unicode 字符的字符串。
  
## <a name="return-value"></a>返回值

返回一 **个 xltypeStr** 字符串，其中包含传入字符串缓冲区的副本。 
  
## <a name="remarks"></a>备注

请注意 **，XLOPER** 字符串 Framework 函数 **TempStr** 的行为不同，并尝试使用后续字符串的长度覆盖所提供字符串的第一个字符。 这并不总是一个安全的方法：如果传递了只读字符串，Microsoft Excel 可能会崩溃。 这种创建临时字符串的方法现已弃用，支持 **TempStrConst** 和 **TempStr12 的** 正常工作方式。 因此，输入字符串的第一个字符被视为字符串的开头，即不作为长度字符或长度字符的空格。 不应传递在开始时编码有长度字符的字符串，因为后果可能是不可预知的。 
  
## <a name="example"></a>示例

此示例使用 **TempStr12** 函数为消息框创建字符串。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempStrExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempStr12Const(L"Made it!"));
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

