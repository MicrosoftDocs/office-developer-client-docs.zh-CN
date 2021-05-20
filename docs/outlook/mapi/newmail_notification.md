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
ms.openlocfilehash: 25af1c1b05618d4f36a43721e71be6ff5c7c597f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439854"
---
# <a name="newmail_notification"></a>NEWMAIL_NOTIFICATION

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述与新邮件到达有关的信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> **lpEntryID** 成员指向的条目标识符中的字节数。 
    
 **lpEntryID**
  
> 指向新到达的邮件的条目标识符的指针。
    
 **cbParentID**
  
> **lpParentID** 成员指向的条目标识符中的字节数。 
    
 **lpParentID**
  
> 指向新到达的邮件的接收文件夹的条目标识符的指针。
    
 **ulFlags**
  
> 用于描述邮件中包含的字符串属性格式的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 **lpszMessageClass**
  
> 指向新到达的邮件的邮件类的指针。 
    
 **ulMessageFlags**
  
> 描述新到达的邮件的当前状态的标志的位掩码。 **ulMessageFlags** 成员是 [PidTagMessageFlags PR_MESSAGE_FLAGS (PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 的副本。 
    
## <a name="remarks"></a>备注

the **NEWMAIL_NOTIFICATION** structure is one of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure. 当 **NOTIFICATION** 结构的信息成员包含一个 NEWMAIL_NOTIFICATION **结构时****，NOTIFICATION** 结构的 **ulEventType** 成员将设置为 _fnevNewMail。_
  
MAPI 仅使用 **NEWMAIL_NOTIFICATION** 结构作为 **NOTIFICATION** 结构的成员，该结构保存有关通知接收器的通知事件的信息。 
  
有关通知详细信息，请参阅下表中介绍的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论服务提供商如何使用 [IMAPISupport](imapisupportiunknown.md) 方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[NOTIFICATION](notification.md)
  
[PidTagMessageFlags 规范属性](pidtagmessageflags-canonical-property.md)


[MAPI 结构](mapi-structures.md)

