---
title: TempActiveCell/TempActiveCell12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempActiveCell
- TempActiveCell12
keywords:
- tempactivecell12 函数 [excel 2007]，TempActiveCell 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: ac5a200d-32d5-4313-9a6d-d730032aaf10
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f9bdb4cd9919d0e52654a3996ede99c4d1b35cc6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413190"
---
# <a name="tempactivecelltempactivecell12"></a>TempActiveCell/TempActiveCell12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
创建包含对活动工作表上单元格的外部引用的临时 /  **XLOPER XLOPER12** 的框架库函数。 
  
```cs
LPXLOPER TempActiveCell(WORD row, BYTE col);
LPXLOPER12 TempActiveCell12(RW row, COL co);
```

## <a name="parameters"></a>参数

 _row_
  
要引用的行。 行参数从零开始，因此行 1 作为 0 传递。 在 Microsoft Office Excel 2003 及更早版本中，从 Excel 2007 开始在兼容模式下运行工作簿，最大值为 65，535 = 2^16 - 1，并且是 WORD 整数可以取的最大值。 从 2007 Excel工作簿开始，最大值为 1，048，575 = 2^20 - 1。 RW 在 XLCALL.H 中定义为 32 位有符号整数。
  
 _col_
  
要引用的列。 这是从零开始，以便列 A 作为 0 传递。 在 Excel 2003 及更早版本中，从 Excel 2007 开始，在兼容模式下运行工作簿时，最大值为 255 = 2^8 - 1，它是 BYTE 整数可以取的最大值。 从 2007 Excel工作簿开始，最大值为 16，383 = 2^14 - 1。 COL 在 XLCALL.H 中定义为 32 位有符号整数。
  
## <a name="return-value"></a>返回值

返回对传入的单元格的 **xltypeRef** 外部引用。 
  
## <a name="example"></a>示例

以下示例使用 **TempActiveCell12** 在活动工作表上显示 B94 的内容。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveCellExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempActiveCell12(93,1));
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

