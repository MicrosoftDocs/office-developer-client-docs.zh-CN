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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421380"
---
# <a name="imapisupportstorelogofftransports"></a>IMAPISupport::StoreLogoffTransports

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
请求有序释放邮件存储。
  
```cpp
HRESULT StoreLogoffTransports(
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [in， out]控制邮件存储注销发生方式的标志的位掩码。 在输入时，此参数的所有标志都是互斥的;每个调用只能设置以下标志之一：
    
LOGOFF_ABORT 
  
> 此存储的任何传输提供程序活动都应在注销之前停止。 在活动停止且 MAPI 后台处理程序注销存储后，控制权将返回到客户端。 如果发生任何传输活动，将不会发生注销，并且 MAPI 后台处理程序或传输提供程序行为不会发生任何更改。 如果当前没有活动，MAPI 后台处理程序将释放存储。 
    
LOGOFF_NO_WAIT 
  
> MAPI 后台处理程序应在准备好发送的所有出站邮件发送后立即释放存储，将控制权返回给客户端。 如果邮件存储具有默认收件箱，则接收任何进程内邮件，然后进一步禁用接收。 
    
LOGOFF_ORDERLY 
  
> MAPI 后台处理程序应在处理完任何待定消息后立即释放存储，将控制权返回给客户端。 不应处理新邮件。 
    
LOGOFF_PURGE 
  
> 工作原理与LOGOFF_NO_WAIT相同。 the LOGOFF_PURGE flag returns control to the caller after completion. 
    
LOGOFF_QUIET 
  
> 如果正在发生任何传输提供程序活动，则不应发生注销。 发生活动的类型在输出时作为标志返回。
    
    On output, MAPI spooler can return one or more of the following flags:
    
LOGOFF_COMPLETE 
  
> 可以完成注销。 与存储关联的所有资源已释放，并且该对象已失效。 MAPI 后台处理程序已执行或将执行所有请求。 此时应仅调用邮件存储 **的 IUnknown：：Release** 方法。 
    
LOGOFF_INBOUND 
  
> 邮件当前正在从一个或多个传输提供程序进入存储区。 
    
LOGOFF_OUTBOUND 
  
> 一个或多个传输提供程序当前正在从存储中发送邮件。 
    
LOGOFF_OUTBOUND_QUEUE 
  
> 当前存在存储的出站队列中的邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注销过程成功。
    
## <a name="remarks"></a>备注

**IMAPISupport：：StoreLogoffTransports** 方法为邮件存储提供程序支持对象实现。 邮件存储提供程序调用 **StoreLogoffTransports，** 以向客户端应用程序提供对 MAPI 在邮件存储关闭时如何处理传输提供程序活动的一些控制。 
  
如果另一个进程对同一配置文件关闭存储，MAPI 将忽略对 **StoreLogoffTransports** 的调用，并返回  _lpulFlags_ 参数LOGOFF_COMPLETE标志 LOGOFF_COMPLETE。 
  
**StoreLogoffTransports** 返回后存储提供程序的行为应基于 _lpulFlags_ 的值，该值指示系统状态并传达有关注销行为的客户端指令。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 通常从存储提供程序的 [IMsgStore：：StoreLogoff](imsgstore-storelogoff.md)方法调用 **StoreLogoffTransports。** 但是，也可以从邮件存储的 **IUnknown：：Release** 方法调用它。 实现 **邮件存储** 的 Release 方法，以便检查是否已发生 **对 StoreLogoffTransports** 的调用。 如果尚未发生呼叫，请调用设置了 LOGOFF_ABORT 标记的 **StoreLogoffTransports。** 
  
_lpulFlags_ 参数设置为指示客户端如何要求关闭邮件存储的标志。 根据对 **StoreLogoff** 的调用中的相应参数的设置，确定 _ulFlags_ 的相应设置。 也就是说，如果客户端调用 **StoreLogoff** 方法，将 _ulFlags_ 设置为 LOGOFF_ORDERLY，则应该调用将 _ulFlags_ 设置为 LOGOFF_ORDERLY 的 **StoreLogoffTransports。** 
  
有关邮件存储注销过程的信息，请参阅 [关闭邮件存储提供程序](shutting-down-a-message-store-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)
  
[IXPLogon::FlushQueues](ixplogon-flushqueues.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

