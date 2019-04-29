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
  
用于将旧**XLOPER**转换为新**XLOPER12**的转换例程。
  
```cs
BOOL XLOperToXLOper12(LPXLOPER pxloper, LPXLOPER12 pxloper12);
```

## <a name="parameters"></a>参数

_pxloper_(**LPXLOPER**)
  
指向要转换的源**XLOPER**的指针。 
  
_pxloper12_(**LPXLOPER12**)
  
指向目标**XLOPER12**的指针, 以包含转换后的值。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果转换成功,**则为 TRUE** , 否则为**FALSE** 。 
  
## <a name="remarks"></a>说明

根据**XLOPER**的类型, 此函数为转换的值分配一个新的内存缓冲区, 这些值指向目标**XLOPER12**中的。 如果转换成功, 则呼叫者负责释放与副本关联的任何内存;可以使用**FreeXLOper12T** , 也可以直接使用**free**执行。
  
如果转换失败, 则呼叫者无需释放任何内存。
  
通常情况下, 可以从任何**XLOPER**转换为**XLOPER12** 。 相比之下, 当**XLOPER12**包含的数组或引用过大或字符串太长而无法包含的**XLOPER**时, 从**XLOPER12**到**XLOPER**的转换可能会失败。 
  
**XLOPER**ASCII 字节字符串将以与区域设置相关的方式转换为**XLOPER12** Unicode 宽字符字符串。 
  
### <a name="example"></a>示例

有关此函数`\SAMPLES\FRAMEWRK\FRAMEWRK.C`的代码, 请参阅文件。 
  

