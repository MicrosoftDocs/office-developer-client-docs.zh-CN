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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d214cb5d449e2f7e42e7ee72774fdc146495adb4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776168"
---
# <a name="lpropcompareprop"></a>LPropCompareProp

  
  
**适用于**： Outlook 
  
比较两个属性值来确定它们是否相等。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LONG LPropCompareProp(
  LPSPropValue lpSPropValueA,
  LPSPropValue lpSPropValueB
);
```

## <a name="parameters"></a>参数

 _lpSPropValueA_
  
> [in]指向[SPropValue](spropvalue.md)结构定义要进行比较的第一个属性值的指针。 
    
 _lpSPropValueB_
  
> [in]指向**SPropValue**结构定义要进行比较的第二个属性值的指针。 
    
## <a name="return-value"></a>返回值

 **LPropCompareProp**返回大多数属性类型的下列值之一： 
  
- 小于零值由_lpSPropValueA_参数小于的_lpSPropValueB_参数指示。 
    
- 大于零，如果值由_lpSPropValueA_为大于由_lpSPropValueB_。
    
- 零，如果值由_lpSPropValueA_等于指示_lpSPropValueB_的值。 
    
对于具有任何固有排序，如布尔值的属性类型或错误类型， **LPropCompareProp**函数返回未定义的值，如果两个属性值不相等。 未定义的该值是跨呼叫非零值和一致。 
  
## <a name="remarks"></a>备注

仅当要进行比较的两个属性的类型都是相同，请使用**LPropCompareProp**函数。 
  
调用之前**LPropCompareProp**，客户端应用程序或服务提供商必须先检索对[IMAPIProp::GetProps](imapiprop-getprops.md)方法的调用与比较的属性。 客户端或提供程序的调用**LPropCompareProp**，该函数首先检查属性标记以确保属性值的比较结果时有效。 然后，该函数比较返回相应值的属性值。 
  
如果属性值不相等， **LPropCompareProp**确定哪一种更高版本。 **LPropCompareProp**比较的属性没有属于相同的对象。 
  

