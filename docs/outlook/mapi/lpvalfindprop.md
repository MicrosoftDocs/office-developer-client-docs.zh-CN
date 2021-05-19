---
title: LpValFindProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 67461a38-bb60-467b-901b-39c645e764f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fa1588d4a58824b57c132fc8e66a0abd6e9acd0a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419637"
---
# <a name="lpvalfindprop"></a>LpValFindProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
搜索属性集内指定的属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序。  <br/> |
   
```cpp
LPSPropValue LpValFindProp(
  ULONG ulPropTag,
  ULONG cValues,
  LPSPropValue lpPropArray
);
```

## <a name="parameters"></a>参数

 _ulPropTag_
  
> [in]属性集内要搜索的属性的标记，由  _lpPropArray_ 参数指示。 
    
 _cValues_
  
> [in]属性集内的属性计数，由  _lpPropArray 参数_ 指示。 
    
 _lpPropArray_
  
> [in] **定义要搜索的属性的 SPropValue** 结构的数组。 
    
## <a name="return-value"></a>返回值

**LpValFindProp** 函数返回 **一个 SPropValue** 结构，该结构定义与输入属性标记匹配的属性;如果没有匹配项，则返回 NULL。 
  
## <a name="remarks"></a>备注

**LpValFindProp** 函数与 **PpropFindProp 相同**。
  
## <a name="see-also"></a>另请参阅



[PpropFindProp](ppropfindprop.md)
  
[SPropValue](spropvalue.md)

