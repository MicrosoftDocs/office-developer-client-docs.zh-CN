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
ms.openlocfilehash: 55cba4f7cfb3fa8035117348b10ab1d6d3082710
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405511"
---
# <a name="spropattrarray"></a>SPropAttrArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含对象属性的属性列表。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage  <br/> |
|相关宏:  <br/> |[CbNewSPropAttrArray](cbnewspropattrarray.md)、 [CbSPropAttrArray](cbspropattrarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cValues;
  ULONG aPropAttr[MAPI_DIM];
} SPropAttrArray, FAR *LPSPropAttrArray;

```

## <a name="members"></a>Members

 **cValues**
  
> **aPropAttr**成员中属性属性的计数。 
    
 **aPropAttr**
  
> 属性属性的数组。 属性的有效值如下所示:
    
    - PROPATTR_MANDATORY
    
    - PROPATTR_READABLE
    
    - PROPATTR_WRITEABLE
    
    - PROPATTR_NOT_PRESENT
    
## <a name="remarks"></a>说明

**SPropAttrArray**结构由实现[IPropData: IMAPIProp](ipropdataimapiprop.md)接口的属性数据对象使用。 MAPI 的 IMAPIMessageSite (即基于结构化存储的[IUnknown](imapimessagesiteiunknown.md) ) 实现也使用它。 
  
## <a name="see-also"></a>另请参阅



[IPropData : IMAPIProp](ipropdataimapiprop.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)
  
[CbNewSPropAttrArray](cbnewspropattrarray.md)
  
[CbSPropAttrArray](cbspropattrarray.md)


[MAPI 结构](mapi-structures.md)

