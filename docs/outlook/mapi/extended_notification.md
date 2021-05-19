---
title: EXTENDED_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.EXTENDED_NOTIFICATION
api_type:
- COM
ms.assetid: f01fce7b-a038-4002-8bad-0e6a51ae9d05
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8b49d0b80102f6295f3f717fb123a6581854d5a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415717"
---
# <a name="extended_notification"></a>EXTENDED_NOTIFICATION

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述与特定于服务提供商的事件相关的信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _EXTENDED_NOTIFICATION
{
  ULONG ulEvent;
  ULONG cb;
  LPBYTE pbEventParameters;
} EXTENDED_NOTIFICATION;

```

## <a name="members"></a>Members

 **ulEvent**
  
> 提供程序定义的扩展事件代码。
    
 **cb**
  
> **pbEventParameters** 指向的事件特定参数中的字节数。 
    
 **pbEventParameters**
  
> 指向特定于事件的参数的指针。 使用的参数类型取决于 **ulEvent 成员** 的值;这些参数由发出事件的提供程序记录。 
    
## <a name="remarks"></a>备注

the **EXTENDED_NOTIFICATION** structure is one of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure. 当 **NOTIFICATION** 结构的信息成员包含一个 EXTENDED_NOTIFICATION **结构时****，NOTIFICATION** 结构的 **ulEventType** 成员将设置为 _fnevExtended_。
  
扩展事件由服务提供商定义，以表示任何其他预定义事件无法覆盖的一种更改类型。 只有先知道服务提供程序支持扩展事件的客户端才能注册该事件。 客户端无法在没有高级知识的情况下确定服务提供商是否支持扩展事件。 如果服务提供商支持扩展事件，则说明当收到该事件时如何处理该事件。
  
客户端注销时，会话将发送扩展通知。 通过调用 [IMAPISession：：Advise](imapisession-advise.md) 注册此通知，  _同时将 lpEntryID_ 参数设置为  _NULL，cbEntryID_ 参数设置为零。 
  
有关通知详细信息，请参阅下表中介绍的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论服务提供商如何使用 [IMAPISupport](imapisupportiunknown.md) 方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[NOTIFICATION](notification.md)


[MAPI 结构](mapi-structures.md)

