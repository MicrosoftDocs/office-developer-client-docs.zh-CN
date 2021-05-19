---
title: TempActiveRef/TempActiveRef12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempActiveRef
- TempActiveRef12
keywords:
- tempactiveref 函数 [excel 2007]，TempActiveRef12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 7c69d15a-294b-4545-983b-720409001e0e
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 58feee8f43e0f90f710c9e4387684dcb6d173a7b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415542"
---
# <a name="tempactivereftempactiveref12"></a>TempActiveRef/TempActiveRef12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
创建临时 **XLOPER** /  **XLOPER12** 的框架库函数，其中包含对活动工作表上单元格矩形块的外部引用。 
  
```cs
LPXLOPER TempActiveRef(WORD rwFirst, WORD rwLast, BYTE colFirst, BYTE colLast);
LPXLOPER12 TempActiveRef12(ROW rwFirst, ROW rwLast, COL colFirst, COL colLast);
```

## <a name="parameters"></a>参数

 _rwFirst_
  
引用的起始行。
  
 _rwLast_
  
引用的结束行。
  
行参数从零开始，因此行 1 作为 0 传递。 在 Microsoft Office Excel 2003 及更早版本中，从 Excel 2007 开始在兼容模式下运行工作簿，最大值为 65，535 = 2^16 - 1，并且是 WORD 整数可以取的最大值。 从 2007 Excel工作簿开始，最大值为 1，048，575 = 2^20 - 1。 RW 在 XLCALL.H 中定义为 32 位有符号整数。
  
 _colFirst_
  
引用的起始列号。
  
 _colLast_
  
引用的结束列号。
  
列参数从零开始，以便列 A 作为 0 传递。 在 Excel 2003 及更早版本中，从 Excel 2007 开始，在兼容模式下运行工作簿时，最大值为 255 = 2^8 - 1，它是 BYTE 整数可以取的最大值。 从 2007 Excel工作簿开始，最大值为 16，383 = 2^14 - 1。 COL 在 XLCALL.H 中定义为 32 位有符号整数。
  
## <a name="return-value"></a>返回值

返回对传入的单元格矩形块的 **xltypeRef** 外部引用。 
  
## <a name="example"></a>示例

此示例使用 **TempActiveRef12** 函数选择单元格 A105：C110。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveRefExample(void)
{
    Excel12f(xlcSelect, 0, 1, TempActiveRef12(104, 109, 0, 2));
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

