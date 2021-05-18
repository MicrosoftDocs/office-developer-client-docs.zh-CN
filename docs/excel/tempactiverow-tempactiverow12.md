---
title: TempActiveRow/TempActiveRow12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempActiveRow
- TempActiveRow12
keywords:
- tempactiverow 函数 [excel 2007]，TempActiveRow12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: cbb9181c-59b0-4133-a085-94a94ac3f229
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 1f89c458a521b41e4f172f8a6c53526440bb472b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413106"
---
# <a name="tempactiverowtempactiverow12"></a>TempActiveRow/TempActiveRow12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
创建临时 **XLOPER XLOPER12** 的框架库函数，其中包含对活动工作表上整行 /  的外部引用。 
  
```cs
LPXLOPER TempActiveRow(WORD row);
LPXLOPER12 TempActiveRow12(ROW row);
```

## <a name="parameters"></a>参数

 _row_
  
要引用的行。 行参数从零开始，因此行 1 作为 0 传递。 在 Microsoft Office Excel 2003 及更早版本中，从 Excel 2007 开始在兼容模式下运行工作簿，最大值为 65，535 = 2^16 - 1，并且是 WORD 整数可以取的最大值。 从 2007 Excel工作簿开始，最大值为 1，048，575 = 2^20 - 1。 RW 在 XLCALL.H 中定义为 32 位有符号整数。
  
## <a name="return-value"></a>返回值

返回对传入的行单元格的 **xltypeRef** 外部引用。 
  
## <a name="example"></a>示例

此示例使用 **TempActiveRow12** 函数选择第 113 行。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveRowExample(void)
{
   Excel12f(xlcSelect, 0, 1, TempActiveRow12(112));
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

