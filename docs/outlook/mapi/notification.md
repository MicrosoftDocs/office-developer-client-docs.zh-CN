---
title: NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.NOTIFICATION
api_type:
- COM
ms.assetid: 01b6e695-a649-4efd-a893-7586b476467e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0d427adde72c24d4ca879c7bd883af09c4ecad53
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579968"
---
# <a name="notification"></a>NOTIFICATION
 
**适用于**： Outlook 2013 |Outlook 2016 
  
包含有关发生的事件和受事件的数据的信息。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct
{
  ULONG ulEventType;
  union
  {
    ERROR_NOTIFICATION err;
    NEWMAIL_NOTIFICATION newmail;
    OBJECT_NOTIFICATION obj;
    TABLE_NOTIFICATION tab;
    EXTENDED_NOTIFICATION ext;
    STATUS_OBJECT_NOTIFICATION statobj;
  } info;
} NOTIFICATION, FAR *LPNOTIFICATION;

```

## <a name="members"></a>Members

**ulEventType**
  
> 通知事件发生的类型。 **UlEventType**成员的值对应于**info**联合中包含的结构。 **UlEventType**成员可以设置为下列值之一： 
    
 _fnevCriticalError_
  
> 全局发生的错误，如会话正在关闭。 **Info**成员包含[ERROR_NOTIFICATION](error_notification.md)结构。 
    
 _fnevExtended_
  
> 特定服务提供程序定义的内部事件发生。 **Info**成员包含[EXTENDED_NOTIFICATION](extended_notification.md)结构。 
    
 _fnevNewMail_
  
> 已将消息发送到相应的接收文件夹的邮件类和正在等待处理。 **Info**成员包含[NEWMAIL_NOTIFICATION](newmail_notification.md)结构。 
    
 _fnevObjectCopied_
  
> 已复制的 MAPI 对象。 **Info**成员包含[OBJECT_NOTIFICATION](object_notification.md)结构。 
    
 _fnevObjectCreated_
  
> 已创建一个 MAPI 对象。 **Info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevObjectDeleted_
  
> MAPI 对象已被删除。 **Info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevObjectModified_
  
> MAPI 对象已更改。 **Info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevObjectMoved_
  
> 消息存储或地址簿对象已移动。 **Info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevSearchComplete_
  
> 完成搜索操作并且可结果。 **Info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevTableModified_
  
> 已更改表中的信息。 **Info**成员包含[TABLE_NOTIFICATION](table_notification.md)结构。 
    
**信息**
  
> 描述受影响的数据的特定类型的事件通知结构的联合。 **Info**成员中包含的结构取决于**ulEventType**成员的值。 
    
## <a name="remarks"></a>注解

一个或多个**通知**结构与每个呼叫的注册的 advise 接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法传递作为输入参数。 **通知**结构包含有关的特定事件的发生和描述受影响的对象的信息。 
  
客户端或接收通知的服务提供商可以使用结构处理该事件之前，它们必须检查的事件类型， **ulEventType**成员中所述。 例如，此处检查到达新消息和在检测这种类型的事件时显示的代码示例将输出的邮件的邮件类。 
  
```cpp
if (pNotif -> ulEventType == fnevNewMail)
{
printf("%s\n", pNotif -> newmail.lpszMessageClass)
}

```

有关通知的详细信息，请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论了客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论的服务提供程序如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅


- [ERROR_NOTIFICATION](error_notification.md)  
- [EXTENDED_NOTIFICATION](extended_notification.md)  
- [NEWMAIL_NOTIFICATION](newmail_notification.md)  
- [OBJECT_NOTIFICATION](object_notification.md)  
- [STATUS_OBJECT_NOTIFICATION](status_object_notification.md)  
- [TABLE_NOTIFICATION](table_notification.md)
- [MAPI 结构](mapi-structures.md)

