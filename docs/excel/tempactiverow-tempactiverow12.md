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
- tempactiverow 函数 [excel 2007，] TempActiveRow12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: cbb9181c-59b0-4133-a085-94a94ac3f229
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a406d6e5a8ffa91e103276cb39230058b4840614
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773811"
---
# <a name="tempactiverowtempactiverow12"></a>TempActiveRow/TempActiveRow12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
创建临时**XLOPER**的框架库函数/ **XLOPER12**包含对活动工作表的整行的外部引用。 
  
```cs
LPXLOPER TempActiveRow(WORD row);
LPXLOPER12 TempActiveRow12(ROW row);
```

## <a name="parameters"></a>参数

 _row_
  
要引用的行。 行参数是从零开始的所以第 1 行传递为 0。 在 Microsoft Office Excel 2003 和早期版本，以及开始在兼容模式下运行的工作簿的 Excel 2007 中的最大值是 65535 = 2 ^16-1，WORD 整数可以采取的最大值。 启动运行工作簿的 Excel 2007 中的最大值是 1048575 = 2 ^20-1。 RW 被定义为 XLCALL 中的 32 位有符号整数。H。
  
## <a name="return-value"></a>返回值

返回对传入的行单元格的**xltypeRef**外部引用。 
  
## <a name="example"></a>示例

本示例使用**TempActiveRow12**函数选择行 113。 
  
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

