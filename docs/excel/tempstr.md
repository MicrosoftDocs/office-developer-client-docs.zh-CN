---
title: TempStr
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempStr
keywords:
- tempstr 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b21b4868-babe-4255-9093-503172efa045
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4ccb6f3c764371c35bac12c8c78fede54234a7d6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418041"
---
# <a name="tempstr"></a>TempStr

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
弃用的 Framework 库函数, 用于创建包含**xltypeStr**字节字符串的临时**XLOPER** 。 它采用以 null 结尾的源字符串作为输入。 它尝试使用后面的字符串的长度覆盖所提供的字符串的第一个字符。 但这并不总是安全的事情: 如果传递只读字符串, Microsoft Excel 可能会崩溃。 
  
```cs
LPXLOPER TempStr(LPSTR str);
```

## <a name="parameters"></a>参数

 _str_
  
指向以 null 结尾的源字符串的指针。 **TempStr**截断超过255字节的字符串。 
  
## <a name="return-value"></a>返回值

返回一个**xltypeStr**字符串, 该字符串包含指向传入的字符串缓冲区的指针。 
  
## <a name="remarks"></a>说明

这种创建临时字符串的方法现在已被弃用, 取而代之的是[TempStrConst 和 TempStr12](tempstrconst-tempstr12.md)的工作方式。 这些函数分配一个新的内存缓冲区, 并将传入的字符串复制到该缓冲区中。 **TempStrConst**和**TempStr12**的输入字符串不会发生更改, 因此声明为**const**。 相比之下, **TempStr**的输入字符串已更改, 因此不能声明为**const**。 输入字符串的第一个字符被视为长度字符的空格, 并被此函数覆盖。
  
## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

