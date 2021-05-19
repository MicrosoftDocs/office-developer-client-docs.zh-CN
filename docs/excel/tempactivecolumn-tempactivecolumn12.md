---
title: TempActiveColumn/TempActiveColumn12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempActiveColumn
- TempActiveColumn12
keywords:
- tempactivecolumn12 函数 [excel 2007]，TempActiveColumn 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 4b1f34c4-e7fa-4a0b-8fc5-c9d465ebb70c
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d1399a407e3e269b78c7afbde8ff32c126b4b1bc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417873"
---
# <a name="tempactivecolumntempactivecolumn12"></a>TempActiveColumn/TempActiveColumn12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
创建临时 **XLOPER XLOPER12** 的框架库函数，其中包含对活动工作表上整个 /  列的外部引用。 
  
```cs
LPXLOPER TempActiveColumn(BYTE col);
LPXLOPER12 TempActiveColumn12(COL col);
```

## <a name="parameters"></a>参数

 _col_ (**BYTE**) 
  
要引用的列。 这是从零开始，以便列 A 作为 0 传递。 在 Microsoft Office Excel 2003 及更早版本中，从在兼容模式下运行工作簿的 Excel 2007 开始，最大值为 255 = 2^8 - 1，它是 BYTE 整数可以取的最大值。 从 2007 Excel工作簿开始，最大值为 16，383 = 2^14 - 1。 COL 在 XLCALL.H 中定义为 32 位有符号整数。
  
## <a name="return-value"></a>返回值

返回对传入的列的 **xltypeRef** 外部引用。 
  
## <a name="example"></a>示例

以下示例使用 **TempActiveColumn12** 选择整列 B。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveColumnExample(void)
{
    Excel12f(xlcSelect, 0, 1, TempActiveColumn12(1));
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

