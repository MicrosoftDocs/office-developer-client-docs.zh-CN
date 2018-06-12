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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5e23d9b829a941e3add8b8d8e137c73052b08aa6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774904"
---
# <a name="extendednotification"></a>EXTENDED_NOTIFICATION

  
  
**适用于**： Outlook 
  
介绍与服务提供程序特定的事件相关的信息。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _EXTENDED_NOTIFICATION
{
  ULONG ulEvent;
  ULONG cb;
  LPBYTE pbEventParameters;
} EXTENDED_NOTIFICATION;

```

## <a name="members"></a>成员

 **ulEvent**
  
> 定义服务提供商的扩展的事件代码。
    
 **cb**
  
> 由**pbEventParameters**指向特定于事件的参数中的字节数。 
    
 **pbEventParameters**
  
> 指向特定于事件的参数。 使用的参数的类型取决于**ulEvent**成员; 的值这些参数由的提供程序发出事件记录。 
    
## <a name="remarks"></a>备注

**EXTENDED_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。 如果**通知**结构的**信息**成员包含**EXTENDED_NOTIFICATION**结构，**通知**结构的**ulEventType**成员设置为_fnevExtended_。
  
由表示的更改不能包含的任何其他预定义事件类型的服务提供程序定义扩展的事件。 只有知道他们注册服务提供商支持扩展的事件之前的客户端可以注册的事件。 不能为客户端确定高级不知情的情况下，如果服务提供商支持的扩展的事件。 如果服务提供商支持的扩展的事件，它演示如何处理接收时的事件。
  
由客户端注销的会话发送一扩展的通知。 通过调用不带_lpEntryID_参数设置为 NULL 和_cbEntryID_参数设置为零[IMAPISession::Advise](imapisession-advise.md)注册此通知。 
  
有关通知的详细信息，请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论了客户端应如何处理通知。  <br/> |
|[支持的事件通知](supporting-event-notification.md) <br/> |讨论的服务提供程序如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[通知](notification.md)


[MAPI 结构](mapi-structures.md)

