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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348676"
---
# <a name="ipropdatahrsetpropaccess"></a>IPropData::HrSetPropAccess

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置一个或多个对象属性的访问级别或状态。
  
```cpp
HRESULT HrSetPropAccess(
  LPSPropTagArray lpPropTagArray,
  ULONG FAR * rgulAccess
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> 实时指向指示要修改的属性的属性标记数组的指针。 
    
 _rgulAccess_
  
> 实时标记位掩码的数组。 每个位掩码表示_lpPropTagArray_参数所指向的数组中标识的每个属性的访问级别或状态。 这两个数组的位置如下所示: _rgulAccess_中的第一个位掩码描述_lpPropTagArray_指向的第一个属性, 等等。 对于每个属性标记, 可以设置一个访问级别标志和一个状态标志。 下表显示了可能的标志。 
    
|**访问级别标志**|**状态标志**|
|:-----|:-----|
|IPROP_READONLY, 表示无法修改属性  <br/> |IPROP_CLEAN, 指示属性尚未修改。  <br/> |
|IPROP_READWRITE, 指示可以修改属性。  <br/> |IPROP_DIRTY, 指示属性已被修改。  <br/> |
   
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置了访问级别和状态标志。
    
MAPI_E_NO_ACCESS 
  
> 试图设置只读对象或对象的属性, 该对象的调用方没有足够的权限。
    
MAPI_E_INVALID_PARAMETER 
  
> _rgulAccess_参数包含无效的标志组合, 如 IPROP_READONLY 和 IPROP_READWRITE。 
    
## <a name="remarks"></a>注解

**IPropData:: HrSetPropAccess**方法更改由_lpPropTagArray_参数指向的[SPropTagArray](sproptagarray.md)结构中的属性标记所标识的属性的访问级别和状态。 对于每个属性, _rgulAccess_数组中都有对应的条目。 该条目可设置为一个指示属性的访问级别和另一个指示其状态的标志的标志。 
  
## <a name="notes-to-callers"></a>给调用方的说明

使用**HrSetPropAccess**来确定特定属性值何时更改, 并更改一个或多个对象的属性的访问级别。 
  
## <a name="see-also"></a>另请参阅



[SPropTagArray](sproptagarray.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)

