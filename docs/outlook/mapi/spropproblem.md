---
title: SPropProblem
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropProblem
api_type:
- COM
ms.assetid: 55943197-fd11-442d-bb4b-0bff565b846e
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 32aa91d43e4674c0de20a0dbb670dcb9e2c782cf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778849"
---
# <a name="spropproblem"></a>SPropProblem

  
  
**适用于**： Outlook 
  
介绍错误与涉及属性的操作。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SPropProblem
{
  ULONG ulIndex;
  ULONG ulPropTag;
  SCODE scode;
} SPropProblem, FAR *LPSPropProblem;

```

## <a name="members"></a>成员

 **ulIndex**
  
> 属性标记的数组中的索引。
    
 **ulPropTag**
  
> 属性标记具有错误的属性。
    
 **scode**
  
> 描述属性的问题的错误值。 此值可以是任何 MAPI [SCODE](scode.md)值。 
    
## <a name="remarks"></a>备注

从以下方法，则返回**SPropProblem**结构的数组： 
  
- [IMAPISupport::DoCopyTo](imapisupport-docopyto.md)
    
- [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)
    
- [IMAPIProp::DeleteProps](imapiprop-deleteprops.md)
    
- [IMAPIProp::SetProps](imapiprop-setprops.md)
    
- [IMAPIProp::CopyProps](imapiprop-copyprops.md)
    
- [IMAPIProp::CopyTo](imapiprop-copyto.md)
    
- [IPropData::HrAddObjProps](ipropdata-hraddobjprops.md)
    
**SPropProblem**结构包含尝试修改或删除的 MAPI 属性的操作的结果**SCODE**错误值。 
  
有关如何与错误相关属性结合使用**SPropProblem**结构的详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。 
  
## <a name="see-also"></a>另请参阅



[SCODE](scode.md)
  
[SPropProblemArray](spropproblemarray.md)


[MAPI 结构](mapi-structures.md)

