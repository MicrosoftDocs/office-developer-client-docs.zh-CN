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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417656"
---
# <a name="hrsetoneprop"></a>HrSetOneProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置或更改属性接口上单个属性的值，即，派生自 [IMAPIProp 的接口](imapipropiunknown.md)。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HrSetOneProp(
  LPMAPIPROP pmp,
  LPSPropValue pprop
);
```

## <a name="parameters"></a>参数

 _pmp_
  
> [in]指向要设置或更改属性值的 [IMAPIProp](imapipropiunknown.md) 接口的指针。 
    
 _pprop_
  
> [in]指向 [SPropValue](spropvalue.md) 结构的指针，该结构定义在  _pmp_ 属性上设置的值。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

与 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法不同 **，HrSetOneProp** 函数从不返回任何警告。 因为它只设置一个属性，所以它要么成功要么失败。 对于设置或更改多个属性 **，SetProps** 速度更快。 
  
可以使用 [HrGetOneProp](hrgetoneprop.md) 函数检索单个属性。 
  

