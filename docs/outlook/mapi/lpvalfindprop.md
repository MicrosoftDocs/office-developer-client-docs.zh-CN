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
ms.openlocfilehash: d7601eb50818fa6f39384a6b024215fc4917e83a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776150"
---
# <a name="lpvalfindprop"></a>LpValFindProp

  
  
**适用于**： Outlook 
  
搜索属性中指定属性设置。
  
|||
|:-----|:-----|
|头文件：  <br/> |mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商。  <br/> |
   
```cpp
LPSPropValue LpValFindProp(
  ULONG ulPropTag,
  ULONG cValues,
  LPSPropValue lpPropArray
);
```

## <a name="parameters"></a>参数

 _ulPropTag_
  
> [in]标记中的属性集，由_lpPropArray_参数指示搜索的属性。 
    
 _cValues_
  
> [in]属性集，由_lpPropArray_参数中的属性的计数。 
    
 _lpPropArray_
  
> [in]**SPropValue**结构的数组，用于定义要搜索的属性。 
    
## <a name="return-value"></a>返回值

**LpValFindProp**函数将返回**SPropValue**结构，它定义符合输入的属性标记，则为 NULL，如果没有匹配的属性。 
  
## <a name="remarks"></a>说明

**LpValFindProp**函数等同于**PpropFindProp**。
  
## <a name="see-also"></a>另请参阅



[PpropFindProp](ppropfindprop.md)
  
[SPropValue](spropvalue.md)

