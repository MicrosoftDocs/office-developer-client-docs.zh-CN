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
- tempstr12 函数 [excel 2007，] TempStrConst 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: faf4ee4e-8d33-4cb3-ae16-5648a837ee4f
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 321c41aa87a3bfa0edc1d77ecc8fbe4b6a6a4730
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773827"
---
# <a name="tempstrconsttempstr12"></a>TempStrConst/TempStr12

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
创建临时**XLOPER/XLOPER12**的框架库函数包含**xltypeStr**字符串，将作为输入 null 结尾的源字符串。 该函数分配新内存缓冲区，并向其复制传入的字符串。 输入的字符串不会改动，并因此声明为**常量**。
  
```cs
LPXLOPER TempStrConst(const LPSTR str);
LPXLOPER12 TempStr12(const XCHAR* lpstr);
```

## <a name="parameters"></a>参数

 _str_
  
一个指向 null 结尾的源字符串。 对于**XLOPER**的 TempStrConst 截断字符串的长度超过 255 个字节。 对于**XLOPER12**的 TempStr12Const 截断长度大于 32,767 Unicode 字符的字符串。
  
## <a name="return-value"></a>返回值

返回包含字符串中传递缓冲区的副本**xltypeStr**字符串。 
  
## <a name="remarks"></a>备注

请注意**XLOPER**字符串框架函数， **TempStr**，会有所不同，并尝试使用后面的字符串长度覆盖所提供的字符串的第一个字符。 这并不总是安全的做法： 如果传递的只读的字符串，Microsoft Excel 可能崩溃。 创建临时字符串的这种方式以哪些**TempStrConst**和**TempStr12**工作方式应用现已被否决。 因此输入字符串的第一个字符被视为字符串的开头，即不作为长度字符或空格长度字符。 不应将传递已长度字符编码开头，如下后果可能不可预测的字符串。 
  
## <a name="example"></a>示例

本示例使用**TempStr12**函数创建一个消息框的字符串。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempStrExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempStr12Const(L"Made it!"));
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[Framework 库中的函数](functions-in-the-framework-library.md)

