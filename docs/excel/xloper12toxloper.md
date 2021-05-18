---
title: XLOper12ToXLOper
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- XLOper12ToXLOper
keywords:
- xloper12toxloper 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b46f87c4-778b-4502-be57-c3725f73a644
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 148353dcec1cc051aa44d18c0a081b6623e3759a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422906"
---
# <a name="xloper12toxloper"></a>XLOper12ToXLOper

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用于从新 **XLOPER12** 转换为旧 **XLOPER 的转换例程**。
  
```cs
BOOL XLOper12ToXLOper(LPXLOPER12 pxloper12, LPXLOPER pxloper);
```

## <a name="parameters"></a>参数

_pxloper12_ (**LPXLOPER12**) 
  
指向要转换的 **源 XLOPER12** 的指针。 
  
_pxloper_ (**LPXLOPER**) 
  
指向要包含转换 **值的目标 XLOPER** 的指针。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果转换成功，则其为 **TRUE;** 否则为 **FALSE。** 
  
## <a name="remarks"></a>备注

根据 **XLOPER12** 的类型，此函数为转换值分配新的内存缓冲区，这些值指向目标 **XLOPER**。 如果转换成功，调用方负责释放与副本关联的任何内存; **可以使用 FreeXLOperT，** 也可以直接使用免费 **完成**。
  
如果转换失败，则调用方无需释放任何内存。
  
当 XLOPER12 包含的数组或引用过大或字符串太长 **，XLOPER** 无法包含时，从 **XLOPER12** 转换为 **XLOPER** 可能会失败。  
  
**XLOPER12** Unicode 宽字符字符串以依赖于区域设置的方式转换为 **XLOPER** ASCII 字节字符串。 
  
**XLOPER12** **xltypeInt** 是一个 32 位有符号整数，**而 XLOPER** **xltypeInt** 是一个 16 位有符号整数。 当提供的 **XLOPER12** 整数超过 **XLOPER** 整数的限制时，该整数将转换为 8 字节双精度值，并返回类型 **为 xltypeNum** 的 **XLOPER。** 这是此函数更改转换的 **XLOPER** 类型的唯一情况。
  
### <a name="example"></a>示例

有关此  `\SAMPLES\FRAMEWRK\FRAMEWRK.C` 函数的代码，请参阅 文件。 
  
## <a name="see-also"></a>另请参阅

- [框架库中的函数](functions-in-the-framework-library.md)

