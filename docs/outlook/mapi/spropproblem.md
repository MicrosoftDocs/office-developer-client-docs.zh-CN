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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3a0872c94459fc7c24d13e35adf335ef8012182
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407772"
---
# <a name="spropproblem"></a>SPropProblem

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述与涉及属性的操作相关的错误。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SPropProblem
{
  ULONG ulIndex;
  ULONG ulPropTag;
  SCODE scode;
} SPropProblem, FAR *LPSPropProblem;

```

## <a name="members"></a>Members

 **ulIndex**
  
> 属性标记数组中的索引。
    
 **ulPropTag**
  
> 包含错误的属性的属性标记。
    
 **scode**
  
> 描述属性问题的错误值。 此值可以是任何 MAPI [SCODE](scode.md)值。 
    
## <a name="remarks"></a>说明

从以下方法返回**SPropProblem**结构的数组: 
  
- [IMAPISupport::DoCopyTo](imapisupport-docopyto.md)
    
- [IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)
    
- [IMAPIProp::DeleteProps](imapiprop-deleteprops.md)
    
- [IMAPIProp::SetProps](imapiprop-setprops.md)
    
- [IMAPIProp::CopyProps](imapiprop-copyprops.md)
    
- [IMAPIProp::CopyTo](imapiprop-copyto.md)
    
- [IPropData::HrAddObjProps](ipropdata-hraddobjprops.md)
    
**SPropProblem**结构包含一个由尝试修改或删除 MAPI 属性的操作产生的**SCODE**错误值。 
  
有关**SPropProblem**结构如何处理与属性相关的错误的详细信息, 请参阅[MAPI 命名属性](mapi-named-properties.md)。 
  
## <a name="see-also"></a>另请参阅



[SCODE](scode.md)
  
[SPropProblemArray](spropproblemarray.md)


[MAPI 结构](mapi-structures.md)

