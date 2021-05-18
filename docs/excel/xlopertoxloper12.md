---
title: XLOperToXLOper12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- XLOperToXLOper12
keywords:
- xlopertoxloper12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b2d4581b-ebf6-4eba-aa95-69a5a9ee8028
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: c881f5d03c732b6594e0750808cfa35a65127ed0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404594"
---
# <a name="xlopertoxloper12"></a>XLOperToXLOper12

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用于从旧 **XLOPER** 转换到新 **XLOPER12** 的转换例程。
  
```cs
BOOL XLOperToXLOper12(LPXLOPER pxloper, LPXLOPER12 pxloper12);
```

## <a name="parameters"></a>参数

_pxloper_ (**LPXLOPER**) 
  
指向要转换的 **源 XLOPER** 的指针。 
  
_pxloper12_ (**LPXLOPER12**) 
  
指向目标 **XLOPER12 的指针，** 以包含转换后的值。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果转换成功，则其为 **TRUE;** 否则为 **FALSE。** 
  
## <a name="remarks"></a>备注

根据 **XLOPER** 的类型，此函数为目标 **XLOPER12** 中指向的转换值分配新的内存缓冲区。 如果转换成功，调用方负责释放与副本关联的任何内存; **可以使用 FreeXLOper12T，** 也可以直接使用免费 **完成**。
  
如果转换失败，则调用方无需释放任何内存。
  
通常，从任何 **XLOPER 到** **XLOPER12** 的转换都是可能的。 相比之下，当 XLOPER12 包含的数组或引用过大或字符串太长 **，XLOPER** 无法包含时，从 **XLOPER12** 转换到 **XLOPER** 可能会失败。 
  
**XLOPER** ASCII 字节字符串以依赖于区域设置的方式转换为 **XLOPER12** Unicode 宽字符字符串。 
  
### <a name="example"></a>示例

有关此  `\SAMPLES\FRAMEWRK\FRAMEWRK.C` 函数的代码，请参阅 文件。 
  

