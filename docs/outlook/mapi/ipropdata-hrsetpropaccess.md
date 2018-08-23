---
title: IPropDataHrSetPropAccess
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData.HrSetPropAccess
api_type:
- COM
ms.assetid: 02365050-5e8b-437c-925f-4eb0df646356
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d0054e54d56fbe1cc6d6d783ffcd6330d8ab2e6b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564659"
---
# <a name="ipropdatahrsetpropaccess"></a>IPropData::HrSetPropAccess

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
设置访问权限级别或一个或多个对象的属性的状态。
  
```cpp
HRESULT HrSetPropAccess(
  LPSPropTagArray lpPropTagArray,
  ULONG FAR * rgulAccess
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> [in]一个指向数组属性标记，指示要修改的属性。 
    
 _rgulAccess_
  
> [in]一个标志位掩码的数组。 每位掩码指示的访问级别或状态，或同时为每个标识_lpPropTagArray_参数指向该数组中的属性。 两个数组是位置_rgulAccess_中的第一个位掩码介绍的第一个属性的_lpPropTagArray_点到，依此类推。 对于每个属性标记，可以设置一个访问级别标志和一个状态标志。 下表显示了可能的标志。 
    
|**访问级别标志**|**状态标志**|
|:-----|:-----|
|IPROP_READONLY，指示无法修改属性  <br/> |IPROP_CLEAN，这表明该属性不被修改。  <br/> |
|IPROP_READWRITE，指示可以修改的属性。  <br/> |IPROP_DIRTY，这表明该属性已修改。  <br/> |
   
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置访问级别和状态标志。
    
MAPI_E_NO_ACCESS 
  
> 尝试对只读对象或对象对其呼叫者具有权限不足，无法设置属性。
    
MAPI_E_INVALID_PARAMETER 
  
> _RgulAccess_参数包含无效的标志，如 IPROP_READONLY 和 IPROP_READWRITE 组合。 
    
## <a name="remarks"></a>注解

**IPropData::HrSetPropAccess**方法可更改访问级别和属性在_lpPropTagArray_参数指向的[SPropTagArray](sproptagarray.md)结构中的属性标记标识的状态。 对于每个属性， _rgulAccess_数组中没有对应的项。 项可以设为一个标志，指示该属性的访问级别，另一个标志，指示其状态。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要确定特定属性值更改时，并且可以更改一个或多个对象的属性的访问级别，请使用**HrSetPropAccess** 。 
  
## <a name="see-also"></a>另请参阅



[SPropTagArray](sproptagarray.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)

