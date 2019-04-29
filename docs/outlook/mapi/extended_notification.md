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
# <a name="extendednotification"></a>EXTENDED_NOTIFICATION

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍与特定于服务提供程序的事件相关的信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 由提供程序定义的扩展事件代码。
    
 **cb**
  
> 由**pbEventParameters**指向的事件特定参数中的字节数。 
    
 **pbEventParameters**
  
> 指向事件特定参数的指针。 使用的参数类型取决于**ulEvent**成员的值;这些参数由发出事件的提供程序记录。 
    
## <a name="remarks"></a>说明

**EXTENDED_NOTIFICATION**结构是[通知](notification.md)结构的**info**成员中包含的结构联合的成员之一。 当**通知**结构的**info**成员包含**EXTENDED_NOTIFICATION**结构时,**通知**结构的**ulEventType**成员将设置为_fnevExtended_。
  
扩展事件由服务提供程序定义, 以表示不能由任何其他预定义事件覆盖的更改类型。 只有在注册服务提供程序之前知道的客户端支持扩展事件才能为该事件注册。 如果服务提供程序支持一个扩展事件, 则客户端不能确定没有高级知识的情况。 如果服务提供程序支持一个扩展事件, 它将显示如何在收到此类事件时对其进行处理。
  
当客户端注销时, 会话将发送一个扩展通知。 通过调用[IMAPISession:: 建议](imapisession-advise.md)将_lpEntryID_参数设置为 NULL 并将_cbEntryID_参数设置为零, 注册此通知。 
  
有关通知的详细信息, 请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论了如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知的服务提供商。  <br/> |
   
## <a name="see-also"></a>另请参阅



[NOTIFICATION](notification.md)


[MAPI 结构](mapi-structures.md)

