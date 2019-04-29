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
  
用于将新**XLOPER12**转换为旧**XLOPER**的转换例程。
  
```cs
BOOL XLOper12ToXLOper(LPXLOPER12 pxloper12, LPXLOPER pxloper);
```

## <a name="parameters"></a>参数

_pxloper12_(**LPXLOPER12**)
  
指向要转换的源**XLOPER12**的指针。 
  
_pxloper_(**LPXLOPER**)
  
指向目标**XLOPER**的指针, 以包含转换后的值。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果转换成功,**则为 TRUE** , 否则为**FALSE** 。 
  
## <a name="remarks"></a>说明

根据**XLOPER12**的类型, 此函数为转换的值分配一个新的内存缓冲区, 这些值指向目标**XLOPER**中的。 如果转换成功, 则呼叫者负责释放与副本关联的任何内存;可以使用**FreeXLOperT** , 也可以通过使用**free**直接完成。
  
如果转换失败, 则呼叫者无需释放任何内存。
  
当**XLOPER12**包含的数组或引用太大或字符串太长而无法包含的**XLOPER**时, 从**XLOPER12**到**XLOPER**的转换可能会失败。 
  
**XLOPER12**Unicode 宽字符字符串将以与区域设置相关的方式转换为**XLOPER** ASCII 字节字符串。 
  
**XLOPER12** **xltypeInt**是一个32位带符号整数, 而**XLOPER** **xltypeInt**是一个16位带符号整数。 当提供的**XLOPER12**整数超过**XLOPER**整数的限制时, 该整数将转换为8字节双精度, 并在类型**xltypeNum**的**XLOPER**中返回。 在这种情况下, 此函数将更改已转换的**XLOPER**的类型。
  
### <a name="example"></a>示例

有关此函数`\SAMPLES\FRAMEWRK\FRAMEWRK.C`的代码, 请参阅文件。 
  
## <a name="see-also"></a>另请参阅

- [框架库中的函数](functions-in-the-framework-library.md)

