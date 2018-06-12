---
title: ConvertXLRefToXLRef12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- ConvertXLRefToXLRef12
keywords:
- convertxlreftoxlref12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 94580044-9497-425f-a31e-53bb4d94dc30
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: f2830633482e5329d285907b610386b708c406a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773646"
---
# <a name="convertxlreftoxlref12"></a>ConvertXLRefToXLRef12

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
尝试**XLREF**转换**XLREF12**的框架函数。
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF pxRef, LPXLREF12 pxRef12);
```

## <a name="parameters"></a>参数

 _pxRef_(**LPXLREF**)
  
指向源引用结构。
  
 _pxRef12_(**LPXLREF12**)
  
转换后的值是放置到其中的目标引用结构的指针。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

 如果为**TRUE**转换成功， **FALSE**否则。 
  
## <a name="remarks"></a>备注

传入的**XLREF**是有效的则此操作应始终为成功。 相比之下，转换的其他方式从**XLREF12** **XLREF**，由[ConvertXLRef12ToXLRef](convertxlref12toxlref.md)，执行失败提供的引用引用的 Excel 2007 工作表中不支持早期版本中的一部分。
  
## <a name="example"></a>示例

 `\SAMPLES\FRAMEWRK\FRAMEWRK.C`
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF pxref, LPXLREF12 pxref12)
{
   if (pxref->rwLast >= pxref->rwFirst && pxref->colLast >= pxref->colFirst)
   {
      if (pxref->rwFirst >= 0 && pxref->colFirst >= 0)
      {
         pxref12->rwFirst = pxref->rwFirst;
         pxref12->rwLast = pxref->rwLast;
         pxref12->colFirst = pxref->colFirst;
         pxref12->colLast = pxref->colLast;
         return TRUE;
      }
   }
   return FALSE;
}
```

## <a name="see-also"></a>另请参阅



[Framework 库中的函数](functions-in-the-framework-library.md)

