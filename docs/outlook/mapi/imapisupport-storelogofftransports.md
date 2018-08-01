---
title: IMAPISupportStoreLogoffTransports
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.StoreLogoffTransports
api_type:
- COM
ms.assetid: f21fba96-c5ca-4d41-9b93-c7955ab7327f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6624c4abf05dc7df9fc79df43f1d0fe76251d052
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775685"
---
# <a name="imapisupportstorelogofftransports"></a>IMAPISupport::StoreLogoffTransports

  
  
**适用于**： Outlook 
  
请求的消息存储的有序版本。
  
```cpp
HRESULT StoreLogoffTransports(
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [传入、 传出]位掩码的标志，控制如何消息存储注销发生此事件。 在输入时，此参数的所有标志相互都排斥;每次呼叫，可以设置以下标志中的只有一个：
    
LOGOFF_ABORT 
  
> 在注销之前，应停止此存储的任何传输提供程序活动。 停止活动和 MAPI 后台处理程序已关闭存储记录之后，将返回到客户端控制权。 如果任何传输活动正在进行，不会发生注销并 MAPI 后台处理程序或传输提供程序行为中的任何更改。 如果当前没有任何活动，MAPI 后台处理程序释放存储。 
    
LOGOFF_NO_WAIT 
  
> MAPI 后台处理程序应释放存储并立即发送后所有出站邮件可以发送的控制权归还给客户端。 消息存储库具有默认收件箱，如果收到任何进程内邮件，然后禁用进一步接收。 
    
LOGOFF_ORDERLY 
  
> MAPI 后台处理程序应释放存储并返回到客户端的控件，任何挂起的邮件已完成后，立即处理。 应处理没有新邮件。 
    
LOGOFF_PURGE 
  
> 适用于 LOGOFF_NO_WAIT 标志相同。 LOGOFF_PURGE 标志完成后返回到呼叫者的控件。 
    
LOGOFF_QUIET 
  
> 如果任何传输提供程序活动正在进行，不应发生注销。 正在进行的活动的类型输出返回作为的标志。
    
    On output, MAPI spooler can return one or more of the following flags:
    
LOGOFF_COMPLETE 
  
> 可以完成注销。 已发布与存储关联的所有资源，并已失效对象。 MAPI 后台处理程序已执行，或将执行所有请求。 应在此时调用仅的消息存储**IUnknown::Release**方法。 
    
LOGOFF_INBOUND 
  
> 邮件当前来自到存储一个或多个传输提供程序。 
    
LOGOFF_OUTBOUND 
  
> 由一个或多个传输提供程序从存储是当前正在发送一条消息。 
    
LOGOFF_OUTBOUND_QUEUE 
  
> 存储的出站队列中当前没有消息。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注销过程成功。
    
## <a name="remarks"></a>说明

消息存储提供程序支持对象的实现**IMAPISupport::StoreLogoffTransports**方法。 消息存储提供程序调用**StoreLogoffTransports**以提供一些控制如何 MAPI 句柄传输的消息存储提供程序活动正在关闭的客户端应用程序。 
  
如果另一个进程要被注销打开的同一配置文件的存储，MAPI 将忽略**StoreLogoffTransports**调用，返回的标志 LOGOFF_COMPLETE _lpulFlags_参数中。 
  
关注**StoreLogoffTransports**从返回的存储提供程序的行为应基于_lpulFlags_，指示系统状态和传达注销行为的客户端说明的值。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **StoreLogoffTransports**通常从存储提供程序的[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)方法调用。 但是，它也可以调用从消息存储库的**IUnknown::Release**方法。 发生的消息存储以便您可以检查**StoreLogoffTransports**调用**Release**方法的实现。 如果未发生呼叫，呼叫**StoreLogoffTransports**设置了 LOGOFF_ABORT 标志。 
  
_LpulFlags_参数设置为一个标志，指示如何客户端要求要关闭的消息存储。 确定_ulFlags_基于对**StoreLogoff**的调用中的相应参数设置为适当的设置。 即，如果客户端调用，设置为 LOGOFF_ORDERLY _ulFlags_ **StoreLogoff**方法，您应与_ulFlags_设置为 LOGOFF_ORDERLY 调用**StoreLogoffTransports** 。 
  
有关邮件存储注销过程的详细信息，请参阅[关机的情况下消息存储提供程序](shutting-down-a-message-store-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)
  
[IXPLogon::FlushQueues](ixplogon-flushqueues.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

