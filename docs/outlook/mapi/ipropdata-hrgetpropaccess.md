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
  
检索对象的一个或多个属性的访问级别和状态。
  
```cpp
HRESULT HrGetPropAccess(
  LPSPropTagArray FAR * lppPropTagArray,
  ULONG FAR * FAR * lprgulAccess
);
```

## <a name="parameters"></a>参数

 _lppPropTagArray_
  
> [in， out]在输入时，一组属性标记，用于指示要检索其访问级别和状态的属性;否则为指向 NULL 的指针，指示 **HrGetPropAccess 应** 检索所有属性的访问级别和状态。 输出时，检索其访问和状态标志的属性标记数组。 标志存储在  _lprgulAccess_ 参数指向的数组中。 
    
 _lprgulAccess_
  
> [out]指向标志位掩码数组的指针。 每个位掩码都指示  _lpPropTagArray_ 参数指向的数组中标识的每个属性的访问级别或状态（或两者）。 这两个数组是位置数组，其中  _lprgulAccess 指向_ 的第一个位掩码描述  _lpPropTagArray_ 指向的第一个属性，以此类比。 对于每个属性标记，可以设置以下标志： 
    
|**访问级别标志**|**状态标志**|
|:-----|:-----|
|IPROP_READONLY，指示无法修改属性。  <br/> |IPROP_CLEAN，指示属性尚未修改。  <br/> |
|IPROP_READWRITE，指示可以修改属性。  <br/> |IPROP_DIRTY，指示属性已修改。  <br/> |
   
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回属性的访问级别和状态标志。
    
## <a name="remarks"></a>备注

**IPropData：：HrGetPropAccess** 方法检索一组指示一个或多个属性的访问级别和状态的标志。 
  
## <a name="notes-to-callers"></a>调用者注意：

可以将 **HrGetPropAccess** 用于以下目的： 
  
- 确定客户端是否更改或删除了可写属性。
    
- 防止客户端使用 [IMAPIProp](imapipropiunknown.md) 方法更改或删除属性。 
    
如果  _lppPropTagArray_ 指向的属性标记数组中的某个属性已被删除， **则 HrGetPropAccess** 在输出时将数组条目设置为 0。 如果将  _lppPropTagArray_ 设置为 NULL，并且对象的属性之一已被删除，则数组中将返回已删除的属性。 
  
如果属性已修改，则其 IPROP_DIRTY 标志在  _lprgulAccess 指向_ 的数组的相应条目中设置。 既不IPROP_READONLY设置IPROP_READWRITE，也不会设置任何设置。 
  
如果属性尚未修改或删除，将仅IPROP_READONLY或IPROP_READWRITE属性标记。 
  
## <a name="see-also"></a>另请参阅



[SPropTagArray](sproptagarray.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)

