---
title: GetInstance
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.GetInstance
api_type:
- COM
ms.assetid: cb432d52-6c96-45d2-bbde-45b0de3f915c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 936a20c4236ab76e5acdb178737c3044d3f53bfe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418720"
---
# <a name="getinstance"></a>GetInstance

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将多值属性中的一个值复制到同一类型的单值属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |MAPIUTIL。水平  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
VOID GetInstance(
  LPSPropValue pvalMv,
  LPSPropValue pvalSv,
  ULONG uliInst
);
```

## <a name="parameters"></a>参数

 _pvalMv_
  
> 实时指向定义多值属性的[SPropValue](spropvalue.md)结构的指针。 
    
 _pvalSv_
  
> 实时指向用于接收数据的单值属性的指针。 
    
 _uliInst_
  
> 实时从_pvalMv_参数指示的结构中复制的值的实例号, 即数组元素。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

如果复制的值对于分配的内存来说太大, 则**GetInstance**函数仅复制指针, 而不是分配新内存。 
  

