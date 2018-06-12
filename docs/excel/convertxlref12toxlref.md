---
title: ConvertXLRef12ToXLRef
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- ConvertXLRef12ToXLRef
keywords:
- convertxlref12toxlref 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b620ed21-73ef-489b-9c00-7be12bb41214
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 826428edb57eba9e17d601164aa8b4b797fc8929
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773639"
---
# <a name="convertxlref12toxlref"></a>ConvertXLRef12ToXLRef

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
尝试**XLREF12**转换**XLREF**。
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF12 pxRef12, LPXLREF pxRef);
```

## <a name="parameters"></a>参数

 _pxRef12_(**LPXLREF12**)
  
指向源引用结构。
  
 _pxRef_(**LPXLREF**)
  
转换后的值是放置到其中的目标引用结构的指针。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

 如果为**TRUE**转换成功， **FALSE**否则。 
  
## <a name="remarks"></a>备注

如果提供的引用是指不支持早期版本中的 Excel 2007 工作表部分，从**XLREF12**到**XLREF**的转换失败。 
  
## <a name="example"></a>示例

 `\SAMPLES\FRAMEWRK\FRAMEWRK.C`
  
```cs
BOOL ConvertXLRef12ToXLRef(LPXLREF12 pxref12, LPXLREF pxref)
{
   if (pxref12->rwLast >= pxref12->rwFirst && pxref12->colLast >= pxref12->colFirst)
   {
      if (pxref12->rwFirst >=0 && pxref12->colFirst >= 0)
      {
         if (pxref12->rwLast < rwMaxO8 && pxref12->colLast < colMaxO8)
         {
            pxref->rwFirst = (WORD)pxref12->rwFirst;
            pxref->rwLast = (WORD)pxref12->rwLast;
            pxref->colFirst = (BYTE)pxref12->colFirst;
            pxref->colLast = (BYTE)pxref12->colLast;
            return TRUE;
         }
      }
   }
   return FALSE;
}
```

## <a name="see-also"></a>另请参阅



[Framework 库中的函数](functions-in-the-framework-library.md)

