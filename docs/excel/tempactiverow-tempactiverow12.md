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
- tempactiverow 函数 [excel 2007], TempActiveRow12 函数 [excel 2007]
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
  
框架库函数, 用于创建一个临时的**XLOPER**/ **XLOPER12** , 其中包含对活动工作表中整行的外部引用。 
  
```cs
LPXLOPER TempActiveRow(WORD row);
LPXLOPER12 TempActiveRow12(ROW row);
```

## <a name="parameters"></a>参数

 _行_
  
要引用的行。 行参数从零开始, 以便将行1作为0传递。 在 Microsoft Office Excel 2003 及更早版本中, 在兼容模式下运行工作簿的 excel 2007 中, 最大值为 65535 = 2 ^ 16-1, 是单词整数可以采用的最大值。 从运行工作簿的 Excel 2007 开始, 最大值为 1048575 = 2 ^ 20-1。 RW 在 xlcall.h 中定义为32位有符号整数。水平.
  
## <a name="return-value"></a>返回值

返回对传入的行单元格的**xltypeRef**外部引用。 
  
## <a name="example"></a>示例

此示例使用**TempActiveRow12**函数选择行113。 
  
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

