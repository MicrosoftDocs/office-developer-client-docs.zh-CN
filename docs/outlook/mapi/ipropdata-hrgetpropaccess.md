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
ms.openlocfilehash: 8441a4898659a5cd278265cb0199bb9097244aa3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776009"
---
# <a name="ipropdatahrgetpropaccess"></a>IPropData::HrGetPropAccess

  
  
**适用于**： Outlook 
  
检索的访问级别和一个或多个对象的属性的状态。
  
```cpp
HRESULT HrGetPropAccess(
  LPSPropTagArray FAR * lppPropTagArray,
  ULONG FAR * FAR * lprgulAccess
);
```

## <a name="parameters"></a>参数

 _lppPropTagArray_
  
> [传入、 传出]在输入数组属性标记，指示要为其检索访问级别和状态; 属性否则为为 NULL，表明**HrGetPropAccess**应检索访问级别和的所有属性的状态的指针。 输出，检索到数组属性标记为哪些访问和状态标志。 Flags 存储在_lprgulAccess_参数指向的数组。 
    
 _lprgulAccess_
  
> [输出]一个指向数组标志位掩码。 每位掩码指示的访问级别或状态，或同时为每个标识_lpPropTagArray_参数指向该数组中的属性。 两个数组是位置_lprgulAccess_指向介绍的第一个属性的第一个位掩码的_lpPropTagArray_ points 为，依此类推。 对于每个属性标记，可以设置以下标志： 
    
|**访问级别标志**|**状态标志**|
|:-----|:-----|
|IPROP_READONLY，指示无法修改的属性。  <br/> |IPROP_CLEAN，这表明该属性不被修改。  <br/> |
|IPROP_READWRITE，指示可以修改的属性。  <br/> |IPROP_DIRTY，这表明该属性已修改。  <br/> |
   
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的属性的访问级别和状态标志。
    
## <a name="remarks"></a>说明

**IPropData::HrGetPropAccess**方法检索一组标志指示的访问级别和一个或多个属性的状态。 
  
## <a name="notes-to-callers"></a>调用方注释：

您可以使用**HrGetPropAccess**出于以下目的： 
  
- 若要确定客户端是否更改或删除可写属性。
    
- 若要防止更改或删除属性使用[IMAPIProp](imapipropiunknown.md)方法客户端。 
    
如果一个指向_lppPropTagArray_属性标记数组中的属性已被删除， **HrGetPropAccess**设置为 0 具有输出的数组项。 如果_lppPropTagArray_设为 NULL，一个对象的属性已被删除时，则数组中返回的已删除的属性。 
  
如果已修改的属性，其 IPROP_DIRTY 标志设置在数组中对应的项的_lprgulAccess_点为。 IPROP_READONLY 和 IPROP_READWRITE 都不会将设置。 
  
如果未修改或删除属性，将设置仅 IPROP_READONLY 或 IPROP_READWRITE 标志。 
  
## <a name="see-also"></a>另请参阅



[SPropTagArray](sproptagarray.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)

