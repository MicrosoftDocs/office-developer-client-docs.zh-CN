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
ms.openlocfilehash: e176f280cbe15b9c15697b03eb9738887c2924c9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406323"
---
# <a name="ssubrestriction"></a>SSubRestriction

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述用于筛选邮件的附件或收件人表的行的子对象限制。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _SSubRestriction
{
  ULONG ulSubObject;
  LPSRestriction lpRes;
} SSubRestriction;

```

## <a name="members"></a>Members

 **ulSubObject**
  
> 要用作限制目标的子对象的类型。 可能的值如下所示: 
    
PR_MESSAGE_RECIPIENTS 
  
> 将限制应用于邮件的收件人表。 
    
PR_MESSAGE_ATTACHMENTS 
  
>  将限制应用于邮件的附件表。 
    
 **lpRes**
  
> 指向[SRestriction](srestriction.md)结构的指针。 
    
## <a name="remarks"></a>说明

不是所有表都支持子对象限制。 通常情况下, 只有 "文件夹内容" 表和 "搜索结果" 文件夹支持它们。 例如, 子对象限制用于查找具有特定类型的附件或收件人的邮件。 
  
如果某一实现不支持子对象限制, 则它将从其[IMAPITable:: Restrict](imapitable-restrict.md)或[IMAPITable:: FindRow](imapitable-findrow.md)方法返回 MAPI_E_TOO_COMPLEX。 
  
有关限制的工作原理的一般讨论, 请参阅[关于限制](about-restrictions.md)。 
  
## <a name="see-also"></a>另请参阅



[SRestriction](srestriction.md)


[MAPI 结构](mapi-structures.md)

