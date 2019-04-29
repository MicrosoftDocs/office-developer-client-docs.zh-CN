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
ms.openlocfilehash: a3235c2305d61318f482943167e5f307e5da0d70
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432875"
---
# <a name="notification"></a>NOTIFICATION
 
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关已发生的事件和受事件影响的数据的信息。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 发生的通知事件的类型。 **ulEventType**成员的值对应于**info**联合中包含的结构。 **ulEventType**成员可设置为以下值之一: 
    
 _fnevCriticalError_
  
> 发生全局错误, 如正在进行中的会话关闭。 **info**成员包含[ERROR_NOTIFICATION](error_notification.md)结构。 
    
 _fnevExtended_
  
> 特定服务提供程序定义的内部事件已发生。 **info**成员包含[EXTENDED_NOTIFICATION](extended_notification.md)结构。 
    
 _fnevNewMail_
  
> 邮件已传递到邮件类的相应接收文件夹, 并且正在等待处理。 **info**成员包含[NEWMAIL_NOTIFICATION](newmail_notification.md)结构。 
    
 _fnevObjectCopied_
  
> MAPI 对象已复制。 **info**成员包含[OBJECT_NOTIFICATION](object_notification.md)结构。 
    
 _fnevObjectCreated_
  
> 已创建 MAPI 对象。 **info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevObjectDeleted_
  
> MAPI 对象已被删除。 **info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevObjectModified_
  
> MAPI 对象已更改。 **info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevObjectMoved_
  
> 已移动邮件存储或通讯簿对象。 **info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevSearchComplete_
  
> 搜索操作已完成, 结果可用。 **info**成员包含**OBJECT_NOTIFICATION**结构。 
    
 _fnevTableModified_
  
> 表中的信息已更改。 **info**成员包含[TABLE_NOTIFICATION](table_notification.md)结构。 
    
**info**
  
> 通知结构的联合, 用于描述特定类型事件的受影响数据。 **info**成员中包含的结构取决于**ulEventType**成员的值。 
    
## <a name="remarks"></a>说明

每次调用已注册的通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法时, 都会将一个或多个**通知**结构作为输入参数进行传递。 **通知**结构包含有关已发生的特定事件的信息, 并描述受影响的对象。 
  
在接收通知的客户端或服务提供程序可以使用结构处理事件之前, 必须按照**ulEventType**成员中的指示检查事件类型。 例如, 此处显示的代码示例检查新邮件的到达, 并在检测到此类事件时, 输出邮件的邮件类。 
  
```cpp
if (pNotif -> ulEventType == fnevNewMail)
{
printf("%s\n", pNotif -> newmail.lpszMessageClass)
}

```

有关通知的详细信息, 请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论了如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知的服务提供商。  <br/> |
   
## <a name="see-also"></a>另请参阅


- [ERROR_NOTIFICATION](error_notification.md)  
- [EXTENDED_NOTIFICATION](extended_notification.md)  
- [NEWMAIL_NOTIFICATION](newmail_notification.md)  
- [OBJECT_NOTIFICATION](object_notification.md)  
- [STATUS_OBJECT_NOTIFICATION](status_object_notification.md)  
- [TABLE_NOTIFICATION](table_notification.md)
- [MAPI 结构](mapi-structures.md)

