---
title: LPropCompareProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.LPropCompareProp
api_type:
- COM
ms.assetid: f14ad568-fe45-4875-957d-415d39dc6f28
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7417ddeb814cafb954d5ab80a6dae771fd0f7a79
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414611"
---
# <a name="lpropcompareprop"></a>LPropCompareProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对两个属性值进行比较, 以确定它们是否相等。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
LONG LPropCompareProp(
  LPSPropValue lpSPropValueA,
  LPSPropValue lpSPropValueB
);
```

## <a name="parameters"></a>参数

 _lpSPropValueA_
  
> 实时指向一个[SPropValue](spropvalue.md)结构的指针, 该结构定义要比较的第一个属性值。 
    
 _lpSPropValueB_
  
> 实时指向一个**SPropValue**结构的指针, 该结构定义要比较的第二个属性值。 
    
## <a name="return-value"></a>返回值

 对于大多数属性类型, **LPropCompareProp**返回以下值之一: 
  
- 如果_lpSPropValueA_参数指示的值小于_lpSPropValueB_参数所指定的值, 则小于零。 
    
- 如果_lpSPropValueA_指示的值大于_lpSPropValueB_所指示的值, 则大于零。
    
- 如果_lpSPropValueA_指示的值等于_lpSPropValueB_指示的值, 则为零。 
    
对于没有内在排序的属性类型 (如 Boolean 或错误类型), 如果两个属性值不相等, **LPropCompareProp**函数将返回一个未定义的值。 此未定义的值在各个调用中是非零和一致的。 
  
## <a name="remarks"></a>说明

仅当要比较的两个属性的类型相同时, 才使用**LPropCompareProp**函数。 
  
在调用**LPropCompareProp**之前, 客户端应用程序或服务提供程序必须先检索属性以与对[IMAPIProp:: GetProps](imapiprop-getprops.md)方法的调用进行比较。 当客户端或提供程序调用**LPropCompareProp**时, 该函数将首先检查属性标记, 以确保属性值的比较有效。 然后, 该函数将比较属性值, 并返回适当的值。 
  
如果属性值不相等, **LPropCompareProp**将确定哪一个是较大的值。 **LPropCompareProp**比较的属性不必属于同一个对象。 
  

