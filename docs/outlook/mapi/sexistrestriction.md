---
title: SExistRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SExistRestriction
api_type:
- COM
ms.assetid: 48d5ab42-ee70-4f6e-9184-18d22b08ea1b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 62b5a42a540a4fb96761c45cd51c510f12225e9e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778770"
---
# <a name="sexistrestriction"></a>SExistRestriction

  
  
**适用于**： Outlook 
  
介绍用于测试的特定属性作为表中的列存在是否存在限制。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SExistRestriction
{
  ULONG ulReserved1;
  ULONG ulPropTag;
  ULONG ulReserved2;
} SExistRestriction;

```

## <a name="members"></a>Members

 **ulReserved1**
  
> 保留;必须为零。 
    
 **ulPropTag**
  
> 标识要测试的各行中存在的列的属性标记。
    
 **ulReserved2**
  
> 保留;必须为零。
    
## <a name="remarks"></a>说明

存在限制用于保证涉及属性，如属性和内容的限制的限制其他类型的有意义的结果。 时涉及属性限制传递给[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)属性不存在，将不明确的限制结果。 通过创建加入带存在限制在属性限制**和**限制，呼叫者可以保证准确的结果。 
  
存在限制不能用于具有类型 PT_OBJECT 的子对象属性。 
  
有关**SExistRestriction**结构的详细信息，请参阅[有关限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

