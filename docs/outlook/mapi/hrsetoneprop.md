---
title: HrSetOneProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrSetOneProp
api_type:
- COM
ms.assetid: 14ae3242-fddf-4199-a9a7-4ab153b31064
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 37e6560d859ce4731b7a06e571eb38eb160c3686
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347766"
---
# <a name="hrsetoneprop"></a>HrSetOneProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置或更改属性接口上单个属性的值, 即从[IMAPIProp](imapipropiunknown.md)派生的接口。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HrSetOneProp(
  LPMAPIPROP pmp,
  LPSPropValue pprop
);
```

## <a name="parameters"></a>参数

 _pmp_
  
> 实时指向要在其上设置或更改属性值的[IMAPIProp](imapipropiunknown.md)接口的指针。 
    
 _pprop_
  
> 实时指向[SPropValue](spropvalue.md)结构的指针, 该结构定义要在_pmp_属性上设置的值。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

与[IMAPIProp:: SetProps](imapiprop-setprops.md)方法不同, **HrSetOneProp**函数永远不会返回任何警告。 由于它仅设置一个属性, 它只是 "成功" 或 "失败"。 若要设置或更改多个属性, **SetProps**速度更快。 
  
您可以使用[HrGetOneProp](hrgetoneprop.md)函数检索单个属性。 
  

