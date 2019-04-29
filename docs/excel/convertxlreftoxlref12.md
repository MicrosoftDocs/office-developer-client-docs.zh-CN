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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 530cb9cce5b0023318ff6b8a0ff73472f8250aa3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432028"
---
# <a name="convertxlreftoxlref12"></a>ConvertXLRefToXLRef12

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
试图将**XLREF**转换为**XLREF12**的 Framework 函数。
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF pxRef, LPXLREF12 pxRef12);
```

## <a name="parameters"></a>参数

 _pxRef_(**LPXLREF**)
  
指向源引用结构的指针。
  
 _pxRef12_(**LPXLREF12**)
  
指向将在其中放置转换后的值的目标参考结构的指针。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

 如果转换成功,**则为 TRUE** , 否则为**FALSE** 。 
  
## <a name="remarks"></a>说明

如果传入的**XLREF**是有效的, 则此操作应始终成功。 相比之下, 如果所提供的引用引用的是早期版本中不支持的 Excel 2007 工作表的一部分, 则通过[ConvertXLRef12ToXLRef](convertxlref12toxlref.md)执行的另一种从**XLREF12**到**XLREF**的转换将失败。
  
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



[框架库中的函数](functions-in-the-framework-library.md)

