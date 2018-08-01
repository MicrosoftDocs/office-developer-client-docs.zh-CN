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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: ce9399168d5b94d10481d2d0b5b69dd2e1d1d2e9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773824"
---
# <a name="tempstr"></a>TempStr

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
创建包含**xltypeStr**字节字符串临时**XLOPER**的弃用的 Framework 库函数。 它将 null 结尾的源字符串作为输入。 它会尝试使用后面的字符串长度覆盖所提供的字符串的第一个字符。 这并不总是安全的做法： 如果传递的只读的字符串，Microsoft Excel 可能崩溃。 
  
```cs
LPXLOPER TempStr(LPSTR str);
```

## <a name="parameters"></a>参数

 _str_
  
一个指向 null 结尾的源字符串。 **TempStr**截断字符串的长度超过 255 个字节。 
  
## <a name="return-value"></a>返回值

返回包含一个指向传入的字符串缓冲区**xltypeStr**字符串。 
  
## <a name="remarks"></a>说明

创建临时字符串的这种方式以的两个[TempStrConst 和 TempStr12](tempstrconst-tempstr12.md)工作方式应用现已被否决。 这些函数分配新内存缓冲区，并复制到它的传入的字符串。 **TempStrConst**和**TempStr12**的输入的字符串不会改动，并因此声明为**常量**。 相比之下， **TempStr**的输入的字符串更改，因此不能声明为**const**。 输入字符串的第一个字符视为长度字符的空间，并覆盖此函数。
  
## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

