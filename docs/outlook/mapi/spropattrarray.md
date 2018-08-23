---
title: SPropAttrArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropAttrArray
api_type:
- COM
ms.assetid: 30dd19d9-0840-49e9-aec6-ec8d19b1f91d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8f4e62a8eb1b5e61cb0223c66b921e15ab9423b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577679"
---
# <a name="spropattrarray"></a>SPropAttrArray

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含对象的属性的属性的列表。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Imessage.h  <br/> |
|相关的宏：  <br/> |[CbNewSPropAttrArray](cbnewspropattrarray.md) [CbSPropAttrArray](cbspropattrarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cValues;
  ULONG aPropAttr[MAPI_DIM];
} SPropAttrArray, FAR *LPSPropAttrArray;

```

## <a name="members"></a>Members

 **cValues**
  
> 在**aPropAttr**成员中声明 property 属性的计数。 
    
 **aPropAttr**
  
> 一个 property 属性的数组。 属性的有效值如下所示：
    
    - PROPATTR_MANDATORY
    
    - PROPATTR_READABLE
    
    - PROPATTR_WRITEABLE
    
    - PROPATTR_NOT_PRESENT
    
## <a name="remarks"></a>注解

**SPropAttrArray**结构由实现的属性数据对象[IPropData: IMAPIProp](ipropdataimapiprop.md)接口。 MAPI 的实现还使用[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md) ，它是基于结构化的存储。 
  
## <a name="see-also"></a>另请参阅



[IPropData : IMAPIProp](ipropdataimapiprop.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)
  
[CbNewSPropAttrArray](cbnewspropattrarray.md)
  
[CbSPropAttrArray](cbspropattrarray.md)


[MAPI 结构](mapi-structures.md)

