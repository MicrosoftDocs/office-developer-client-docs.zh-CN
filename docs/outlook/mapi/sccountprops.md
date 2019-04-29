---
title: ScCountProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCountProps
api_type:
- COM
ms.assetid: 76e4cc52-e1a0-4e0b-a2a6-a17644f6b2e7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 49634bda487143ddd8d8806b94f6c451ccf57b75
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404972"
---
# <a name="sccountprops"></a>ScCountProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定属性值数组的大小 (以字节为单位), 并验证与该数组关联的内存。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE ScCountProps(
  int cprop,
  LPSPropValue rgprop,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a>参数

 _cprop_
  
> 实时由_rgprop_参数指示的数组中的属性计数。 
    
 _rgprop_
  
> 实时指向[SPropValue](spropvalue.md)结构数组中的区域的指针, 这些结构定义要确定其大小的属性。 此范围不一定从数组的开头开始。 
    
 _pcb_
  
> 排除指向属性数组的大小 (以字节为单位) 的可选指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_INVALID_PARAMETER 
  
> 属性值数组中至少有一个属性的标识符为 PROP_ID_NULL 或 PROP_ID_INVALID, 或者属性数组包含无属性值的多值属性。
    
## <a name="remarks"></a>说明

如果在_pcb_参数中传递 NULL, 则**ScCountProps**函数将验证通知数组, 但不执行任何计算。 如果在_pcb_中传递非 null 值, **ScCountNotifications**函数将确定数组的大小并存储原因_pcb_。 _pcb_参数的大小必须足以包含整个数组。 
  
在进行计数时, **ScCountProps**会验证与该数组关联的内存。 **ScCountProps**仅适用于有关 MAPI 包含其信息的属性。 
  
## <a name="see-also"></a>另请参阅



[PropCopyMore](propcopymore.md)

