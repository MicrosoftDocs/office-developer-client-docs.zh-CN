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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 06cad6e80a2def1c1c3d692a80efeebe0e654a92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776004"
---
# <a name="ipropdatahrsetobjaccess"></a>IPropData::HrSetObjAccess

  
  
**适用于**： Outlook 
  
设置该对象的访问级别。
  
```cpp
HRESULT HrSetObjAccess(
  ULONG ulAccess
);
```

## <a name="parameters"></a>参数

 _ulAccess_
  
> [in]位掩码的标志，指定对象的访问级别。 可以设置以下标志之一：
    
IPROP_READONLY 
  
> 将对象的访问级别设置为只读的。 
    
IPROP_READWRITE 
  
> 设置对象的访问级别，以读/写。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功将对象的访问级别设置。
    
## <a name="remarks"></a>备注

**IPropData::HrSetObjAccess**方法将设置为整个对象，而不是为各个属性的访问级别。 **HrSetObjAccess**可用于更改时创建的对象已建立的访问级别。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要设置属性的某个访问级别，请首先调用_ulAccess_参数中的设置以使该对象可修改了 IPROP_READWRITE 标记**HrSetObjAccess** 。 然后调用[IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md)方法， _lpPropTagArray_参数指向该数组中指定的目标属性。 
  
只读向客户端将与创建对象，创建读/写对象和添加必需属性，然后调用**HrSetObjAccess**更改为只读的对象的访问。 
  
您可以使用**HrSetObjAccess**以防止客户端创建新的属性。 
  
## <a name="see-also"></a>另请参阅



[IPropData::HrGetPropAccess](ipropdata-hrgetpropaccess.md)
  
[IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md)
  
[IPropData: IMAPIProp](ipropdataimapiprop.md)

