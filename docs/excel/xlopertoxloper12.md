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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 76c78e5a2ad62b1a3d1aa23748b10e49e07f6543
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773877"
---
# <a name="xlopertoxloper12"></a>XLOperToXLOper12

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于从旧**XLOPER**转换为新**XLOPER12**转换例程。
  
```cs
BOOL XLOperToXLOper12(LPXLOPER pxloper, LPXLOPER12 pxloper12);
```

## <a name="parameters"></a>参数

_pxloper_(**LPXLOPER**)
  
对源**XLOPER**要转换的指针。 
  
_pxloper12_(**LPXLOPER12**)
  
指向目标**XLOPER12**包含转换的值。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果为**TRUE**转换成功， **FALSE**否则。 
  
## <a name="remarks"></a>说明

根据**XLOPER**类型，此函数为转换后的值，指向目标**XLOPER12**中分配新内存缓冲区。 呼叫者负责释放转换为成功; 如果与副本关联任何内存可以使用**FreeXLOper12T** ，或直接使用**免费**即可完成。
  
如果转换失败，则不需要释放的任何内存呼叫者。
  
一般情况下，从任何**XLOPER**转换为**XLOPER12**时可能。 相比之下，从**XLOPER12**到**XLOPER**转换可能会失败时**XLOPER12**包含数组或引用太大或对于**XLOPER**包含太长字符串。 
  
**XLOPER**ASCII 字节字符串转换为**XLOPER12** Unicode 宽字符字符串是区域设置相关的方式。 
  
### <a name="example"></a>示例

请参阅文件`\SAMPLES\FRAMEWRK\FRAMEWRK.C`的此函数的代码。 
  

