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
- tempint12 函数 [excel 2007]，TempInt 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 86d690b8-caca-450d-93f7-69ca4cd1a6e0
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 16a2222dbc51ad9480dbd5941ca2ed13f65b55e2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438748"
---
# <a name="tempinttempint12"></a>TempInt/TempInt12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
创建包含整数的临时 **XLOPER** /  **XLOPER12** 的框架库函数。 
  
```cs
LPXLOPER TempInt(short int i);
LPXLOPER12 TempInt12(int i);
```

## <a name="parameters"></a>参数

 _i_
  
预期的整数值。 请注意 **，XLOPER** 整数是一个 16 位有符号整数 (short int) ，而 **XLOPER12** 整数是一个 32 位有符号整数 ([long] int) 。 
  
## <a name="return-value"></a>返回值

返回一 **个 xltypeInt** 整数，其中包含传入的值。 
  
## <a name="example"></a>示例

此示例使用 **TempInt12** 函数将参数传递给 **xlfGetWorkspace**。
  
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

