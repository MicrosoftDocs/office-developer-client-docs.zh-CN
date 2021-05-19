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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 0a12052a93d030088feb548449955129ff5bdc0f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432651"
---
# <a name="convertxlref12toxlref"></a>ConvertXLRef12ToXLRef

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
尝试将 **XLREF12** 转换为 **XLREF**。
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF12 pxRef12, LPXLREF pxRef);
```

## <a name="parameters"></a>参数

 _pxRef12_ (**LPXLREF12)**
  
指向源引用结构的指针。
  
 _pxRef_ (**LPXLREF**) 
  
指向要放置转换值的目标引用结构的指针。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

 如果转换成功，则其为 **TRUE;** 否则为 **FALSE。** 
  
## <a name="remarks"></a>备注

如果所提供的引用引用了早期版本中不支持的 Excel 2007 工作表的一部分，则从 **XLREF12** 到 **XLREF** 的转换将失败。 
  
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



[框架库中的函数](functions-in-the-framework-library.md)

