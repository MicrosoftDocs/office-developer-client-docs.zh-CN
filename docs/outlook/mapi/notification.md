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
  
包含有关已发生事件以及受事件影响的数据的信息。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 发生的通知事件的类型。 **ulEventType** 成员的值对应于信息联合 **中包含的结构。** **ulEventType** 成员可以设置为下列值之一： 
    
 _fnevCriticalError_
  
> 发生全局错误，例如会话正在关闭。 信息 **成员**[包含ERROR_NOTIFICATION结构](error_notification.md)。 
    
 _fnevExtended_
  
> 发生了由特定服务提供商定义的内部事件。 信息 **成员**[包含EXTENDED_NOTIFICATION结构](extended_notification.md)。 
    
 _fnevNewMail_
  
> 邮件已传递到邮件类相应的接收文件夹，正在等待处理。 信息 **成员**[包含NEWMAIL_NOTIFICATION结构](newmail_notification.md)。 
    
 _fnevObjectCopied_
  
> 已复制 MAPI 对象。 **信息** 成员 [包含OBJECT_NOTIFICATION结构](object_notification.md)。 
    
 _fnevObjectCreated_
  
> 已创建 MAPI 对象。 **信息** 成员 **包含OBJECT_NOTIFICATION结构**。 
    
 _fnevObjectDeleted_
  
> 已删除 MAPI 对象。 **信息** 成员 **包含OBJECT_NOTIFICATION结构**。 
    
 _fnevObjectModified_
  
> MAPI 对象已更改。 **信息** 成员 **包含OBJECT_NOTIFICATION结构**。 
    
 _fnevObjectMoved_
  
> 已移动邮件存储或通讯簿对象。 **信息** 成员 **包含OBJECT_NOTIFICATION结构**。 
    
 _fnevSearchComplete_
  
> 搜索操作已完成且结果可用。 **信息** 成员 **包含OBJECT_NOTIFICATION结构**。 
    
 _fnevTableModified_
  
> 表中的信息已更改。 信息 **成员**[包含TABLE_NOTIFICATION结构](table_notification.md)。 
    
**info**
  
> 描述特定类型事件受影响的数据的通知结构联合。 信息 **成员中包含的结构** 取决于 **ulEventType** 成员的值。 
    
## <a name="remarks"></a>备注

每次调用注册的通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法时，一个或多个 **NOTIFICATION** 结构都作为输入参数传递。 **NOTIFICATION** 结构包含有关已发生特定事件的信息，并描述了受影响的对象。 
  
在接收通知的客户端或服务提供商可以使用结构处理事件之前，他们必须检查 **ulEventType** 成员中指示的事件类型。 例如，此处显示的代码示例将检查新邮件的到达时间，在检测到此类事件时，将输出邮件的邮件类别。 
  
```cpp
if (pNotif -> ulEventType == fnevNewMail)
{
printf("%s\n", pNotif -> newmail.lpszMessageClass)
}

```

有关通知详细信息，请参阅下表中介绍的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论服务提供商如何使用 [IMAPISupport](imapisupportiunknown.md) 方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅


- [ERROR_NOTIFICATION](error_notification.md)  
- [EXTENDED_NOTIFICATION](extended_notification.md)  
- [NEWMAIL_NOTIFICATION](newmail_notification.md)  
- [OBJECT_NOTIFICATION](object_notification.md)  
- [STATUS_OBJECT_NOTIFICATION](status_object_notification.md)  
- [TABLE_NOTIFICATION](table_notification.md)
- [MAPI 结构](mapi-structures.md)

