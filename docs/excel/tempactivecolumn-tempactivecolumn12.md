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
- tempactivecolumn12 函数 [excel 2007], TempActiveColumn 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 4b1f34c4-e7fa-4a0b-8fc5-c9d465ebb70c
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d1399a407e3e269b78c7afbde8ff32c126b4b1bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310469"
---
# <a name="tempactivecolumntempactivecolumn12"></a>TempActiveColumn/TempActiveColumn12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
框架库函数, 用于创建一个临时的**XLOPER**/ **XLOPER12** , 其中包含对活动工作表上的整个列的外部引用。 
  
```cs
LPXLOPER TempActiveColumn(BYTE col);
LPXLOPER12 TempActiveColumn12(COL col);
```

## <a name="parameters"></a>参数

 _col_(**字节**)
  
要引用的列。 这是从零开始的, 以便将列 A 作为0传递。 在 Microsoft Office Excel 2003 及更早版本中, 在兼容模式下运行工作簿的 excel 2007 中, 最大值为 255 = 2 ^ 8-1, 是字节整数可以采用的最大值。 从运行工作簿的 Excel 2007 开始, 最大值为 16383 = 2 ^ 14-1。 COL 在 xlcall.h 中定义为32位有符号整数。水平.
  
## <a name="return-value"></a>返回值

返回对传入的列的**xltypeRef**外部引用。 
  
## <a name="example"></a>示例

下面的示例使用**TempActiveColumn12**选择整个列 B。 
  
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

