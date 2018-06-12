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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 97dad50fed4179526e46381c4d9ea9d12d568377
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778715"
---
# <a name="sccountprops"></a>ScCountProps

  
  
**适用于**： Outlook 
  
确定大小，以字节为单位，属性值数组，并验证与数组关联的内存。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScCountProps(
  int cprop,
  LPSPropValue rgprop,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a>参数

 _cprop_
  
> [in]由_rgprop_参数指示在阵列中的属性的计数。 
    
 _rgprop_
  
> [in]在范围定义的属性，其大小是确定[SPropValue](spropvalue.md)结构的数组中的指针。 此范围不一定是启动数组的开头。 
    
 _pcb_
  
> [输出]指向的大小，以字节为单位属性数组的可选指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_INVALID_PARAMETER 
  
> 属性值数组中的至少一个属性具有 PROP_ID_NULL 或 PROP_ID_INVALID，标识符或属性数组包含任何属性值的多值的属性。
    
## <a name="remarks"></a>备注

如果_pcb_参数中传递 NULL，则**ScCountProps**函数验证通知的数组，但没有计数完成。 如果在_pcb_传递一个非空值，则**ScCountNotifications**函数确定数组的大小，并将存储原因_pcb_。 _Pcb_参数必须为足够大，使其包含整个数组。 
  
对其进行计数，如**ScCountProps**验证与数组关联的内存。 **ScCountProps**只适用于有关哪些 MAPI 包含信息的属性。 
  
## <a name="see-also"></a>另请参阅



[PropCopyMore](propcopymore.md)

