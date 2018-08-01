---
title: TempInt/TempInt12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempInt
- TempInt12
keywords:
- tempint12 函数 [excel 2007，] TempInt 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 86d690b8-caca-450d-93f7-69ca4cd1a6e0
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: eb1dd9be0c0b20e533d9cd8202f8878c43b997be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773821"
---
# <a name="tempinttempint12"></a>TempInt/TempInt12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
创建临时**XLOPER**的框架库函数/ **XLOPER12**包含一个整数。 
  
```cs
LPXLOPER TempInt(short int i);
LPXLOPER12 TempInt12(int i);
```

## <a name="parameters"></a>参数

 _我_
  
预期的整数值。 请注意， **XLOPER**整数 16 位有符号的整数 (短 int)，而**XLOPER12**整数是一个有符号的 32 位整数 ([长] int)。 
  
## <a name="return-value"></a>返回值

返回一个包含中传递的值的**xltypeInt**整数。 
  
## <a name="example"></a>示例

本示例使用**TempInt12**函数将参数传递给**xlfGetWorkspace**。
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempIntExample(void)
{
    XLOPER12 xRes;
    Excel12f(xlfGetWorkspace, (LPXLOPER12)&xRes, 1, TempInt12(44));
    Excel12f(xlFree, 0, 1, (LPXLOPER12)&xRes);
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

