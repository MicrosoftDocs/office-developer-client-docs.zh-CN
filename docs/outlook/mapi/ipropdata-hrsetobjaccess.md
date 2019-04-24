---
title: IPropDataHrSetObjAccess
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData.HrSetObjAccess
api_type:
- COM
ms.assetid: 01bd3235-22cc-4ff3-b2b6-341ce622128b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4e478c9e8978125a37691ee5bd97fa9f1cbce077
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348690"
---
# <a name="ipropdatahrsetobjaccess"></a>IPropData::HrSetObjAccess

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置对象的访问级别。
  
```cpp
HRESULT HrSetObjAccess(
  ULONG ulAccess
);
```

## <a name="parameters"></a>参数

 _ulAccess_
  
> 实时指定对象的访问级别的标志的位掩码。 可以设置下列标志之一:
    
IPROP_READONLY 
  
> 将对象的访问级别设置为只读。 
    
IPROP_READWRITE 
  
> 将对象的访问级别设置为 "读/写"。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置对象的访问级别。
    
## <a name="remarks"></a>注解

**IPropData:: HrSetObjAccess**方法设置整个对象的访问级别, 而不是设置各个属性的访问级别。 **HrSetObjAccess**可用于更改创建对象时建立的访问级别。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要设置属性的访问级别, 请先使用_ulAccess_参数中设置的 IPROP_READWRITE 标志调用**HrSetObjAccess** , 使该对象可修改。 然后, 调用[IPropData:: HrSetPropAccess](ipropdata-hrsetpropaccess.md)方法, 在由_lpPropTagArray_参数指向的数组中指定目标属性。 
  
若要创建具有对客户端只读属性的对象, 请创建一个读/写对象, 添加所需的属性, 然后调用**HrSetObjAccess**将该对象的访问权限更改为只读。 
  
您还可以使用**HrSetObjAccess**来阻止客户端创建新属性。 
  
## <a name="see-also"></a>另请参阅



[IPropData::HrGetPropAccess](ipropdata-hrgetpropaccess.md)
  
[IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md)
  
[IPropData : IMAPIProp](ipropdataimapiprop.md)

