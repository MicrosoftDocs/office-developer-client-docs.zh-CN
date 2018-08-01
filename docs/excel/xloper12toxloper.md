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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 2c06102699db8810da803ecc0ddfa30375fcc125
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773862"
---
# <a name="xloper12toxloper"></a>XLOper12ToXLOper

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于从新**XLOPER12**转换为旧**XLOPER**转换例程。
  
```cs
BOOL XLOper12ToXLOper(LPXLOPER12 pxloper12, LPXLOPER pxloper);
```

## <a name="parameters"></a>参数

_pxloper12_(**LPXLOPER12**)
  
对源**XLOPER12**要转换的指针。 
  
_pxloper_(**LPXLOPER**)
  
指向目标**XLOPER**包含转换的值。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果为**TRUE**转换成功， **FALSE**否则。 
  
## <a name="remarks"></a>说明

根据**XLOPER12**类型，此函数为转换后的值，指向目标**XLOPER**中分配新内存缓冲区。 呼叫者负责释放转换为成功; 如果与副本关联任何内存可**FreeXLOperT** ，也可直接通过使用**免费**。
  
如果转换失败，则不需要释放的任何内存呼叫者。
  
**XLOPER12**包含数组或引用太大或对于**XLOPER**包含太长字符串时，从**XLOPER12**到**XLOPER**转换可能会失败。 
  
**XLOPER12**Unicode 宽字符的字符串转换为的方式，它是区域设置相关的**XLOPER** ASCII 字节字符串。 
  
**XLOPER12** **xltypeInt**是 32 位有符号的整数，而**XLOPER** **xltypeInt**是一个 16 位有符号的整数。 时提供的**XLOPER12**整数超出**XLOPER**整数的限制，整数转换为 8 字节 double，并返回类型**xltypeNum** **XLOPER** 。 这是唯一的转换**XLOPER**类型更改顺序此函数的情况。
  
### <a name="example"></a>示例

请参阅文件`\SAMPLES\FRAMEWRK\FRAMEWRK.C`的此函数的代码。 
  
## <a name="see-also"></a>另请参阅

- [框架库中的函数](functions-in-the-framework-library.md)

