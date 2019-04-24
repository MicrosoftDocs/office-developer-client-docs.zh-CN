---
title: UlPropSize
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlPropSize
api_type:
- COM
ms.assetid: 240f1144-0805-4cd1-9e7d-f2a550a2f160
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cc1547ad7d881b707825630f96987d4c40ad4863
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315300"
---
# <a name="ulpropsize"></a>UlPropSize

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回单个属性值的大小。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
ULONG UlPropSize(
  LPSPropValue lpSPropValue
);
```

## <a name="parameters"></a>参数

 _lpSPropValue_
  
> 实时指向定义要度量的属性的[SPropValue](spropvalue.md)结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知来源的错误阻止操作完成。
    
## <a name="remarks"></a>注解

**UlPropSize**函数返回指定属性的属性值的大小 (以字节为单位)。 它不会忽略**SPropValue**结构的其余部分的大小。 
  

