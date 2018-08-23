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
ms.openlocfilehash: c4e5d2847b53988fb75e23fc6c4dfc386ea678f4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579261"
---
# <a name="getinstance"></a>GetInstance

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将一个多值属性中的值复制到同一类型的单值属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |MAPIUTIL。H  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
VOID GetInstance(
  LPSPropValue pvalMv,
  LPSPropValue pvalSv,
  ULONG uliInst
);
```

## <a name="parameters"></a>参数

 _pvalMv_
  
> [in]定义一个多值的属性[SPropValue](spropvalue.md)结构的指针。 
    
 _pvalSv_
  
> [in]指向要接收数据的单值属性。 
    
 _uliInst_
  
> [in]实例数量，即，从结构由_pvalMv_参数指示复制值的数组元素。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

如果复制的值为太大，分配的内存， **GetInstance**函数仅复制指针而不是分配新内存。 
  

