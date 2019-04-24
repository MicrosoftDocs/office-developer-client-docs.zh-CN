---
title: PpropFindProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PpropFindProp
api_type:
- HeaderDef
ms.assetid: f23dd6f4-915b-4fe8-ab3f-6d625c7d6061
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 97021128f92af0486af1ba3125c7843eaa357648
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350728"
---
# <a name="ppropfindprop"></a>PpropFindProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在属性集中搜索指定的属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
LPSPropValue PpropFindProp(
  LPSPropValue rgprop,
  ULONG cprop,
  ULONG ulPropTag
);
```

## <a name="parameters"></a>参数

 _rgprop_
  
> 实时定义要搜索的属性的[SPropValue](spropvalue.md)结构的数组。 
    
 _cprop_
  
> 实时由_rgprop_参数指示的属性集中属性的计数。 
    
 _ulPropTag_
  
> 实时要在由_rgprop_参数指示的属性集中搜索的属性的属性标记。 
    
## <a name="return-value"></a>返回值

 **PpropFindProp**返回一个[SPropValue](spropvalue.md)结构, 该结构定义与输入属性标记相匹配的属性; 如果没有匹配项, 则返回 NULL。 
  
## <a name="remarks"></a>注解

如果给定的属性标记指示 PT_UNSPECIFIED 类型的属性, 则**PpropFindProp**函数仅查找标记中的属性标识符的匹配项。 否则, 它找到整个属性标记的匹配项 (包括属性类型), 并返回标识的属性。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |CContentsTableListCtrl:: BuildDataItem  <br/> |MFCMAPI 使用**PpropFindProp**方法来查找要添加到列表中的属性集的属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

