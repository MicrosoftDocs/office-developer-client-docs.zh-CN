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
ms.openlocfilehash: 31d2be027ef3b58fdd44e71c922677164d352feb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569125"
---
# <a name="hrsetoneprop"></a>HrSetOneProp

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
设置或更改单个属性接口，即接口派生自[IMAPIProp](imapipropiunknown.md)上属性的值。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HrSetOneProp(
  LPMAPIPROP pmp,
  LPSPropValue pprop
);
```

## <a name="parameters"></a>参数

 _pmp_
  
> [in]该属性值为要设置或更改的[IMAPIProp](imapipropiunknown.md)接口的指针。 
    
 _pprop_
  
> [in]定义要对_pmp_属性设置的值的[SPropValue](spropvalue.md)结构的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

不同的[IMAPIProp::SetProps](imapiprop-setprops.md)方法， **HrSetOneProp**函数永远不会返回任何警告。 设置只有一个属性，因为它只是成功或失败。 设置或更改多个属性， **SetProps**是更快。 
  
您可以检索[HrGetOneProp](hrgetoneprop.md)函数的单个属性。 
  

