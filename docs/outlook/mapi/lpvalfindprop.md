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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357426"
---
# <a name="lpvalfindprop"></a>LpValFindProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在属性集中搜索指定的属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapiutil  <br/> |
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
  
> 实时要在属性集中搜索的属性的标记, 由_lpPropArray_参数指示。 
    
 _cValues_
  
> 实时属性集中属性的计数, 由_lpPropArray_参数指示。 
    
 _lpPropArray_
  
> 实时**SPropValue**结构的数组, 这些结构定义要搜索的属性。 
    
## <a name="return-value"></a>返回值

**LpValFindProp**函数返回一个**SPropValue**结构, 该结构定义与输入属性标记匹配的属性; 如果没有匹配项, 则返回 NULL。 
  
## <a name="remarks"></a>注解

**LpValFindProp**函数与**PpropFindProp**相同。
  
## <a name="see-also"></a>另请参阅



[PpropFindProp](ppropfindprop.md)
  
[SPropValue](spropvalue.md)

