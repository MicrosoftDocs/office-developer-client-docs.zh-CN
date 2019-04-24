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
- tempactiveref 函数 [excel 2007], TempActiveRef12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 7c69d15a-294b-4545-983b-720409001e0e
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 58feee8f43e0f90f710c9e4387684dcb6d173a7b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301566"
---
# <a name="tempactivereftempactiveref12"></a>TempActiveRef/TempActiveRef12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Framework library 函数, 该函数创建一个临时**XLOPER**/ **XLOPER12** , 该函数包含对活动工作表上的矩形单元格块的外部引用。 
  
```cs
LPXLOPER TempActiveRef(WORD rwFirst, WORD rwLast, BYTE colFirst, BYTE colLast);
LPXLOPER12 TempActiveRef12(ROW rwFirst, ROW rwLast, COL colFirst, COL colLast);
```

## <a name="parameters"></a>参数

 _rwFirst_
  
引用的起始行。
  
 _rwLast_
  
引用的结束行。
  
行参数从零开始, 以便将行1作为0传递。 在 Microsoft Office Excel 2003 及更早版本中, 在兼容模式下运行工作簿的 excel 2007 中, 最大值为 65535 = 2 ^ 16-1, 是单词整数可以采用的最大值。 从运行工作簿的 Excel 2007 开始, 最大值为 1048575 = 2 ^ 20-1。 RW 在 xlcall.h 中定义为32位有符号整数。水平.
  
 _colFirst_
  
引用的起始列号。
  
 _colLast_
  
引用的结束列号。
  
列参数是从零开始的, 以便将列 A 作为0传递。 在 excel 2003 和早期版本中, 并且在兼容模式下运行工作簿的 excel 2007 中, 最大值为 255 = 2 ^ 8-1, 是字节整数可以采用的最大值。 从运行工作簿的 Excel 2007 开始, 最大值为 16383 = 2 ^ 14-1。 COL 在 xlcall.h 中定义为32位有符号整数。水平.
  
## <a name="return-value"></a>返回值

返回一个**xltypeRef**外部引用, 该引用指向传入的单元格的矩形块。 
  
## <a name="example"></a>示例

此示例使用**TempActiveRef12**函数选择单元格 A105: C110。 
  
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

