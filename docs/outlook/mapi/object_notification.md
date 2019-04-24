---
title: OBJECT_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OBJECT_NOTIFICATION
api_type:
- COM
ms.assetid: de3a2297-e0cc-427b-a978-52bade4d9bce
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c637b3b03a22f208123397f7277cf8968f2509a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279884"
---
# <a name="objectnotification"></a>OBJECT_NOTIFICATION

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关已完成更改 (如复制或修改) 的对象的信息。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _OBJECT_NOTIFICATION
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  ULONG ulObjType;
  ULONG cbParentID;
  LPENTRYID lpParentID;
  ULONG cbOldID;
  LPENTRYID lpOldID;
  ULONG cbOldParentID;
  LPENTRYID lpOldParentID;
  LPSPropTagArray lpPropTagArray;
} OBJECT_NOTIFICATION;

```

## <a name="members"></a>Members

 **cbEntryID**
  
> 由**lpEntryID**成员指向的条目标识符中的字节数。 
    
 **lpEntryID**
  
> 指向受影响对象的条目标识符的指针。
    
 **ulObjType**
  
> 受影响的对象的类型。 可能的类型如下所示:
    
MAPI_STORE 
  
> 邮件存储区。 
    
MAPI_ADDRBOOK 
  
> 通讯簿。 
    
MAPI_FOLDER 
  
> 文件夹.
    
MAPI_ABCONT 
  
> 通讯簿容器。
    
MAPI_MESSAGE 
  
> 消息。
    
MAPI_MAILUSER 
  
> 邮件用户。
    
MAPI_ATTACH 
  
> 附着.
    
MAPI_DISTLIST 
  
> 通讯组列表。
    
MAPI_PROFSECT 
  
> Profile 部分。
    
MAPI_STATUS 
  
> Status 对象。
    
MAPI_SESSION 
  
> Session 对象。
    
 **cbParentID**
  
> 由**lpParentID**成员指向的条目标识符中的字节数。 
    
 **lpParentID**
  
> 指向受影响对象的父级的条目标识符的指针。
    
 **cbOldID**
  
> 由**lpOldID**成员指向的条目标识符中的字节数。 
    
 **lpOldID**
  
> 指向原始对象的条目标识符的指针。 如果事件不需要原始对象, 则此指针可以为 NULL。
    
 **cbOldParentID**
  
> 由**lpOldParentID**成员指向的条目标识符中的字节数。 
    
 **lpOldParentID**
  
> 指向原始对象的父对象的条目标识符的指针。 如果事件不需要原始对象, 则此指针可以为 NULL。
    
 **lpPropTagArray**
  
> 指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含用于标识受事件影响的属性的属性标记。 
    
## <a name="remarks"></a>注解

**OBJECT_NOTIFICATION**结构是[通知](notification.md)结构的**info**成员中包含的结构联合的成员之一。 当**通知**结构的**info**成员包含**OBJECT_NOTIFICATION**结构时,**通知**结构的**ulEventType**成员将设置为以下事件类型之一: 
  
- fnevObjectCreated
    
- fnevObjectModified
    
- fnevObjectDeleted
    
- fnevObjectMoved
    
- fnevObjectCopied
    
- fnevSearchComplete
    
由 fnevSearchComplete 事件类型表示的搜索完成事件指示一个搜索文件夹的域的初始搜索已完成。
  
以下包含有关原始对象的信息的成员仅在 move 事件和 copy 事件中使用。 
  
- **cbOldID**
    
- **lpOldID**
    
- **cbOldParentID**
    
- **lpOldParentID**
    
这些成员不适用于其他类型的事件。
  
有关通知的详细信息, 请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论了如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知的服务提供商。  <br/> |
   
## <a name="see-also"></a>另请参阅



[NOTIFICATION](notification.md)
  
[SPropTagArray](sproptagarray.md)


[MAPI 结构](mapi-structures.md)

