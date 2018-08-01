---
title: SSubRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SSubRestriction
api_type:
- COM
ms.assetid: 5f7012f7-060d-4f2d-bcff-2aa9f6980e71
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 152f3032876d6473f1716afa46507196cd5ecc55
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778870"
---
# <a name="ssubrestriction"></a>SSubRestriction

  
  
**适用于**： Outlook 
  
介绍用于筛选邮件的附件或收件人表的行的子对象限制。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SSubRestriction
{
  ULONG ulSubObject;
  LPSRestriction lpRes;
} SSubRestriction;

```

## <a name="members"></a>Members

 **ulSubObject**
  
> 要用作限制的目标的子对象的类型。 可能值如下所示： 
    
PR_MESSAGE_RECIPIENTS 
  
> 限制应用于邮件的收件人表。 
    
PR_MESSAGE_ATTACHMENTS 
  
>  限制应用于邮件的附件表。 
    
 **lpRes**
  
> 指向[SRestriction](srestriction.md)结构。 
    
## <a name="remarks"></a>说明

所有表不支持子对象的限制。 通常情况下，仅文件夹内容表，搜索结果文件夹支持它们。 例如，子对象限制用来查找具有特定类型的附件或收件人的消息。 
  
如果实现不支持子对象限制，则从其[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)方法返回 MAPI_E_TOO_COMPLEX。 
  
有关限制的工作方式的一般讨论，请参阅[有关限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

