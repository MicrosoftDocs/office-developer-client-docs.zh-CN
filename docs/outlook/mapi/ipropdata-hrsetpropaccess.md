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
ms.openlocfilehash: 9e443302e49bad4a586b657a6de298dafbeefab4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437852"
---
# <a name="ipropdatahrsetpropaccess"></a>IPropData::HrSetPropAccess

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置对象的一个或多个属性的访问级别或状态。
  
```cpp
HRESULT HrSetPropAccess(
  LPSPropTagArray lpPropTagArray,
  ULONG FAR * rgulAccess
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> [in]指向指示要修改的属性的属性标记数组的指针。 
    
 _rgulAccess_
  
> [in]标志位掩码的数组。 每个位掩码都指示  _lpPropTagArray_ 参数指向的数组中标识的每个属性的访问级别或状态或两者。 这两个数组是位置数组  _，rgulAccess_ 中的第一个位掩码描述  _lpPropTagArray_ 指向的第一个属性，以此类比。 对于每个属性标记，可以设置一个访问级别标志和一个状态标志。 下表显示了可能的标志。 
    
|**访问级别标志**|**状态标志**|
|:-----|:-----|
|IPROP_READONLY，指示无法修改属性  <br/> |IPROP_CLEAN，指示属性尚未修改。  <br/> |
|IPROP_READWRITE，指示可以修改属性。  <br/> |IPROP_DIRTY，指示属性已修改。  <br/> |
   
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置访问级别和状态标志。
    
MAPI_E_NO_ACCESS 
  
> 尝试对只读对象或调用方权限不足的对象设置属性。
    
MAPI_E_INVALID_PARAMETER 
  
> _rgulAccess_ 参数包含无效的标志组合，如IPROP_READONLY和IPROP_READWRITE。 
    
## <a name="remarks"></a>备注

**IPropData：：HrSetPropAccess** 方法更改由 _lpPropTagArray_ 参数指向 [的 SPropTagArray](sproptagarray.md)结构中的属性标记标识的属性的访问级别和状态。 对于每个属性  _，rgulAccess_ 数组中都有一个对应的条目。 条目可以设置为一个指示属性的访问级别的标志和另一个指示其状态的标志。 
  
## <a name="notes-to-callers"></a>给调用方的说明

使用 **HrSetPropAccess** 可以确定特定属性值何时更改，并更改一个或多个对象属性的访问级别。 
  
## <a name="see-also"></a>另请参阅



[SPropTagArray](sproptagarray.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)

