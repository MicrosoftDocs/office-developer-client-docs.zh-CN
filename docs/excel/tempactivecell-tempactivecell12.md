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
- tempactivecell12 函数 [excel 2007，] TempActiveCell 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: ac5a200d-32d5-4313-9a6d-d730032aaf10
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 8ad409a76195d67fa61e7991ce6527c40e0a3265
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773810"
---
# <a name="tempactivecelltempactivecell12"></a>TempActiveCell/TempActiveCell12

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
创建临时**XLOPER**的框架库函数/ **XLOPER12**包含外部活动工作表的单元格引用。 
  
```cs
LPXLOPER TempActiveCell(WORD row, BYTE col);
LPXLOPER12 TempActiveCell12(RW row, COL co);
```

## <a name="parameters"></a>参数

 _行_
  
要引用的行。 行参数是从零开始的所以第 1 行传递为 0。 在 Microsoft Office Excel 2003 和早期版本，以及开始在兼容模式下运行的工作簿的 Excel 2007 中的最大值是 65535 = 2 ^16-1，WORD 整数可以采取的最大值。 启动运行工作簿的 Excel 2007 中的最大值是 1048575 = 2 ^20-1。 RW 被定义为 XLCALL 中的 32 位有符号整数。H。
  
 _col_
  
要引用的列。 这是从零开始的因此，列 A 传递为 0。 在 Excel 2003 和早期版本，以及开始在兼容模式下运行的工作簿的 Excel 2007 中的最大值是 255 = 2 ^8-1，字节整数可以采取的最大值。 启动运行工作簿的 Excel 2007 中的最大值是 16,383 = 2 ^14-1。 COL 被定义为 XLCALL 中的 32 位有符号整数。H。
  
## <a name="return-value"></a>返回值

返回对传入的单元格的**xltypeRef**外部引用。 
  
## <a name="example"></a>示例

下面的示例使用**TempActiveCell12**活动工作表中显示的 B94 内容。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveCellExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempActiveCell12(93,1));
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[Framework 库中的函数](functions-in-the-framework-library.md)

