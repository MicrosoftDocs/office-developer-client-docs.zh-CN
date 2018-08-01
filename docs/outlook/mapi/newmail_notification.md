---
title: NEWMAIL_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.NEWMAIL_NOTIFICATION
api_type:
- COM
ms.assetid: 49913050-900a-4b05-84c4-c596a93ce68b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aad4d3be8757ca4cd7719bfd7a53ae8bbf6711f3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776525"
---
# <a name="newmailnotification"></a>NEWMAIL_NOTIFICATION

  
  
**适用于**： Outlook 
  
介绍与新消息的到达相关的信息。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _NEWMAIL_NOTIFICATION
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  ULONG cbParentID;
  LPENTRYID lpParentID;
  ULONG ulFlags;
  LPSTR lpszMessageClass;
  ULONG ulMessageFlags;
} NEWMAIL_NOTIFICATION;

```

## <a name="members"></a>Members

 **cbEntryID**
  
> 由**lpEntryID**成员指向中的项标识符的字节数。 
    
 **lpEntryID**
  
> 为新到达消息的项标识符的指针。
    
 **cbParentID**
  
> 由**lpParentID**成员指向中的项标识符的字节数。 
    
 **lpParentID**
  
> 为新到达消息的接收文件夹的项标识符的指针。
    
 **ulFlags**
  
> 用于描述消息中包含的字符串属性的格式的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 **lpszMessageClass**
  
> 向新到达消息的邮件类的指针。 
    
 **ulMessageFlags**
  
> 位掩码的标志，描述新到达消息的当前状态。 **UlMessageFlags**成员是**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 消息的副本。
    
## <a name="remarks"></a>说明

**NEWMAIL_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。 **通知**结构的**ulEventType**成员时**通知**结构的**信息**成员包含**NEWMAIL_NOTIFICATION**结构，设置为_fnevNewMail。_
  
MAPI 仅将**NEWMAIL_NOTIFICATION**结构用作**通知**结构，其中包含有关通知事件的通知接收器的信息中的成员。 
  
有关通知的详细信息，请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论了客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论的服务提供程序如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[NOTIFICATION](notification.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)


[MAPI 结构](mapi-structures.md)

