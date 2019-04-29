---
title: IPropDataHrGetPropAccess
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData.HrGetPropAccess
api_type:
- COM
ms.assetid: 0101d291-00ca-4f66-b857-75d74b9f91a1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e36cf12b7a5b1643f5a0ec97223030718195a7d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433435"
---
# <a name="ipropdatahrgetpropaccess"></a>IPropData::HrGetPropAccess

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索一个或多个对象属性的访问级别和状态。
  
```cpp
HRESULT HrGetPropAccess(
  LPSPropTagArray FAR * lppPropTagArray,
  ULONG FAR * FAR * lprgulAccess
);
```

## <a name="parameters"></a>参数

 _lppPropTagArray_
  
> [in, out]在输入时, 指明要检索其访问级别和状态的属性的一组属性标记。否则为指向 NULL 的指针, 指示**HrGetPropAccess**应检索所有属性的访问级别和状态。 在输出时, 为其检索访问和状态标志的一组属性标记。 这些标志存储在由_lprgulAccess_参数指向的数组中。 
    
 _lprgulAccess_
  
> 排除指向标志位掩码数组的指针。 每个位掩码表示由_lpPropTagArray_参数所指向的数组中标识的每个属性的访问级别或状态。 这两个数组的位置是_lprgulAccess_指向的第一个位掩码, 它描述_lpPropTagArray_指向的第一个属性, 依此类推。 对于每个属性标记, 可以设置以下标志: 
    
|**访问级别标志**|**状态标志**|
|:-----|:-----|
|IPROP_READONLY, 指示属性不能修改。  <br/> |IPROP_CLEAN, 指示属性尚未修改。  <br/> |
|IPROP_READWRITE, 指示可以修改属性。  <br/> |IPROP_DIRTY, 指示属性已被修改。  <br/> |
   
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回属性的访问级别和状态标志。
    
## <a name="remarks"></a>说明

**IPropData:: HrGetPropAccess**方法检索一组标志, 这些标志指示一个或多个属性的访问级别和状态。 
  
## <a name="notes-to-callers"></a>调用者注意：

您可以使用**HrGetPropAccess**来实现以下目的: 
  
- 确定客户端是否更改或删除了可写属性。
    
- 若要防止客户端使用[IMAPIProp](imapipropiunknown.md)方法来更改或删除属性。 
    
如果_lppPropTagArray_所指向的属性标记数组中的某个属性已被删除, 则**HrGetPropAccess**会在输出中将数组项设置为0。 如果将_lppPropTagArray_设置为 NULL, 并且已删除某个对象的属性, 则会在数组中返回 deleted 属性。 
  
如果已修改某个属性, 则会在_lprgulAccess_指向的数组中对应的条目中设置其 IPROP_DIRTY 标志。 不会设置 IPROP_READONLY, 也不会设置 IPROP_READWRITE。 
  
如果尚未修改或删除某个属性, 将仅设置 IPROP_READONLY 或 IPROP_READWRITE 标志。 
  
## <a name="see-also"></a>另请参阅



[SPropTagArray](sproptagarray.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)

