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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 30c91ec7a5a28b0c270da5223a2a245fb504d8c5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326493"
---
# <a name="imapisupportstorelogofftransports"></a>IMAPISupport::StoreLogoffTransports

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
请求邮件存储的有序释放。
  
```cpp
HRESULT StoreLogoffTransports(
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [in, out]用于控制邮件存储注销发生方式的标志的位掩码。 在输入时, 此参数的所有标志都是互斥的;每次调用只能设置以下任一标志:
    
LOGOFF_ABORT 
  
> 在注销之前, 应停止此存储区的任何传输提供程序活动。 控制在活动停止且 MAPI 后台处理程序已注销存储之后返回到客户端。 如果发生任何传输活动, 则不会发生注销, MAPI 后台处理程序或传输提供程序行为不会发生任何变化。 如果当前没有任何活动, MAPI 后台处理程序将释放该存储区。 
    
LOGOFF_NO_WAIT 
  
> MAPI 后台处理程序应在发送所有可供发送的出站邮件之后立即释放存储, 并将控制权返回给客户端。 如果邮件存储区具有默认收件箱, 则接收任何进程内邮件, 然后禁用进一步的接收。 
    
LOGOFF_ORDERLY 
  
> MAPI 后台处理程序应在任何挂起的邮件完成处理之后立即释放存储并将控制权返回给客户端。 不应处理新邮件。 
    
LOGOFF_PURGE 
  
> 与 LOGOFF_NO_WAIT 标志的工作方式相同。 完成后, LOGOFF_PURGE 标志将控制权返回给调用方。 
    
LOGOFF_QUIET 
  
> 如果发生任何传输提供程序活动, 则不应发生注销。 发生的活动类型将作为输出上的标志返回。
    
    On output, MAPI spooler can return one or more of the following flags:
    
LOGOFF_COMPLETE 
  
> 注销可以完成。 已释放与存储区相关联的所有资源, 并且该对象已失效。 MAPI 后台处理程序已执行或将执行所有请求。 此时, 仅应调用邮件存储区的**IUnknown:: Release**方法。 
    
LOGOFF_INBOUND 
  
> 邮件当前来自一个或多个传输提供程序的存储。 
    
LOGOFF_OUTBOUND 
  
> 邮件当前正由一个或多个传输提供程序从存储发送。 
    
LOGOFF_OUTBOUND_QUEUE 
  
> 当前在出站队列中有适用于存储的邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注销过程成功。
    
## <a name="remarks"></a>注解

为邮件存储提供程序支持对象实现了**IMAPISupport:: StoreLogoffTransports**方法。 邮件存储提供程序调用**StoreLogoffTransports** , 以使客户端应用程序能够控制 MAPI 处理传输提供程序活动 (作为邮件存储区的关闭) 的方式。 
  
如果另一个进程对同一配置文件注销了要打开的存储, MAPI 将忽略对**StoreLogoffTransports**的调用, 并返回_lpulFlags_参数中的标志 LOGOFF_COMPLETE。 
  
**StoreLogoffTransports**返回的存储提供程序的行为应基于_lpulFlags_的值, 这表示系统状态并传达有关注销行为的客户端说明。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **StoreLogoffTransports**通常是从存储提供程序的[IMsgStore:: StoreLogoff](imsgstore-storelogoff.md)方法中调用的。 但是, 也可以从邮件存储的**IUnknown:: Release**方法中调用它。 实现邮件存储的**释放**方法, 以便您可以检查是否发生了对**StoreLogoffTransports**的调用。 如果未发生呼叫, 则调用**StoreLogoffTransports**并设置 LOGOFF_ABORT 标志。 
  
_lpulFlags_参数设置为一个标志, 该标志指示客户端需要如何关闭邮件存储。 根据对**StoreLogoff**的调用中相应参数的设置, 确定_ulFlags_的相应设置。 也就是说, 如果客户端调用**StoreLogoff**方法, _ulFlags_设置为 LOGOFF_ORDERLY, 则应调用_ulFlags_设置为 LOGOFF_ORDERLY 的**StoreLogoffTransports** 。 
  
有关邮件存储注销过程的详细信息, 请参阅[关闭邮件存储提供程序](shutting-down-a-message-store-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)
  
[IXPLogon::FlushQueues](ixplogon-flushqueues.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

