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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ae0d6d58f96738a9686dbdda86336c040c2e2f68
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591680"
---
# <a name="ipropdatahraddobjprops"></a>IPropData::HrAddObjProps

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
添加到对象类型 PT_OBJECT 的一个或多个属性。
  
```cpp
HRESULT HrAddObjProps(
  LPSPropTagArray lpPropTagArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> [in]一个指向数组属性标记，指示要添加的属性。
    
 _lppProblems_
  
> [传入、 传出]在输入，有效的指针，指向[SPropProblemArray](spropproblemarray.md)结构，则为 NULL。 输出，为包含有关无法添加的属性的信息的结构指针的指针或 NULL。 仅当有效指针传递中，则返回指向属性问题数组结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功添加属性。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型以外 PT_OBJECT 传递_lpPropTagArray_参数指向该数组中。 
    
MAPI_E_NO_ACCESS 
  
> 已设置的对象不是以允许读/写权限。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 某些，而不是全部已添加的属性。
    
## <a name="remarks"></a>注解

**IPropData::HrAddObjProps**方法添加到对象类型 PT_OBJECT 的一个或多个属性。 **HrAddObjProps**提供对象属性的[IMAPIProp::SetProps](imapiprop-setprops.md)方法的替代项，因为无法通过调用**SetProps**创建对象属性。 被包含在列表中的[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法返回的属性标记属性标记中添加对象属性结果。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果**HrAddObjProps**返回 MAPI_W_PARTIAL_COMPLETION，并将_lppProblems_设置为有效的指针，检查返回的[SPropProblemArray](spropproblemarray.md)结构，以找出未添加哪些属性。 通常，唯一发生的问题是内存不足。 通过在与之完成时调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放**SPropProblemArray**结构。 
  
若要添加的属性，目标对象必须具有读/写权限。 如果**HrAddObjProps**返回 MAPI_E_NO_ACCESS，不能对对象添加属性，因为它不允许修改。 若要获取对之前调用**HrAddObjProps**对象的读/写权限，请调用[IPropData::HrSetObjAccess](ipropdata-hrsetobjaccess.md) ，并将_ulAccess_参数设置为 IPROP_READWRITE。 
  
## <a name="see-also"></a>另请参阅



[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropTagArray](sproptagarray.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)

