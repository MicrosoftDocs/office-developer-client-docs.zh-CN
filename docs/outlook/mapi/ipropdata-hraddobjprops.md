---
title: IPropDataHrAddObjProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData.HrAddObjProps
api_type:
- COM
ms.assetid: 683cf476-3c02-4b3b-939f-6fff6611f9aa
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: df63f08d3d453575816c4f7ab043f802023e21d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416382"
---
# <a name="ipropdatahraddobjprops"></a>IPropData::HrAddObjProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 PT_OBJECT 类型的一个或多个属性添加到对象中。
  
```cpp
HRESULT HrAddObjProps(
  LPSPropTagArray lpPropTagArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> 实时指向指示要添加的属性的属性标记数组的指针。
    
 _lppProblems_
  
> [in, out]在输入时, 指向[SPropProblemArray](spropproblemarray.md)结构的有效指针或 NULL。 在输出时, 指向指向结构的指针的指针, 该结构包含有关无法添加的属性的信息, 或为 NULL。 仅当传入有效指针时, 才会返回指向属性问题数组结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功添加了属性。
    
MAPI_E_INVALID_TYPE 
  
> 在_lpPropTagArray_参数指向的数组中传递了除 PT_OBJECT 之外的属性类型。 
    
MAPI_E_NO_ACCESS 
  
> 对象已设置为不允许读/写权限。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 添加了一些属性, 但并非全部。
    
## <a name="remarks"></a>说明

**IPropData:: HrAddObjProps**方法将类型为 PT_OBJECT 的一个或多个属性添加到对象中。 **HrAddObjProps**为 object 属性提供了[IMAPIProp:: SetProps](imapiprop-setprops.md)方法的替代方法, 因为不能通过调用**SetProps**来创建对象属性。 添加对象属性将导致属性标记包含在[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法返回的属性标记列表中。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果**HrAddObjProps**返回 MAPI_W_PARTIAL_COMPLETION, 并且您已将_lppProblems_设置为有效指针, 请检查返回的[SPropProblemArray](spropproblemarray.md)结构以找出未添加的属性。 通常情况下, 仅存在内存不足的问题。 完成**SPropProblemArray**结构后, 通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放该结构。 
  
若要添加属性, 目标对象必须具有读/写权限。 如果**HrAddObjProps**返回 MAPI_E_NO_ACCESS, 则不能向该对象添加属性, 因为它不允许进行修改。 若要在调用**HrAddObjProps**之前获取对象的读/写权限, 请调用[IPropData:: HrSetObjAccess](ipropdata-hrsetobjaccess.md)并将_ulAccess_参数设置为 IPROP_READWRITE。 
  
## <a name="see-also"></a>另请参阅



[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropTagArray](sproptagarray.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)

