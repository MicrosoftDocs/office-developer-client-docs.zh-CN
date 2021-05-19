---
title: IMsgStoreStoreLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.StoreLogoff
api_type:
- COM
ms.assetid: 3773c98e-531e-4bdc-a39a-2c3bb7378cd3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: be11c536804682d1baec8188b6d7487c71d411e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424334"
---
# <a name="imsgstorestorelogoff"></a>IMsgStore::StoreLogoff

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启用邮件存储的有序注销。
  
```cpp
HRESULT StoreLogoff(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [in， out]控制从邮件存储注销的标志的位掩码。 在输入时，为此参数设置的所有标志都是互斥的;呼叫者只能为每个呼叫指定一个标志。 以下标志在输入时有效：
    
LOGOFF_ABORT 
  
> 应在注销之前停止此邮件存储的任何传输提供程序活动。 控件在活动停止后返回到调用方。 如果正在发生任何传输提供程序活动，则不会发生注销，并且 MAPI 后台处理程序或传输提供程序的行为不会发生任何变化。 如果传输提供程序活动处于空闲状态，MAPI 后台处理程序将释放存储。 
    
LOGOFF_NO_WAIT 
  
> 在关闭之前，邮件存储不应等待来自传输提供程序的邮件。 将发送准备发送的出站邮件。 如果此存储包含默认收件箱，则接收任何进程内邮件，然后进一步禁用接收。 所有活动完成后，MAPI 后台处理程序将释放存储，并且控制权将立即返回到调用方。 
    
LOGOFF_ORDERLY 
  
> 在关闭之前，邮件存储不应等待传输提供程序的信息。 当前正在处理的邮件已完成，但不处理新邮件。 所有活动完成后，MAPI 后台处理程序将释放存储，并且控制权将立即返回到存储提供程序。 
    
LOGOFF_PURGE 
  
> 注销应该与设置 LOGOFF_NO_WAIT 标志时相同，但应调用相应传输提供程序的 [IXPLogon：：FlushQueues](ixplogon-flushqueues.md) 或 [IMAPIStatus：：FlushQueues](imapistatus-flushqueues.md) 方法。 the LOGOFF_PURGE flag returns control to the caller after completion. 
    
LOGOFF_QUIET 
  
> 如果正在发生任何传输提供程序活动，则不应发生注销。
    
    The following flags are valid on output:
    
LOGOFF_INBOUND 
  
> 入站邮件当前正在到达。
    
LOGOFF_OUTBOUND 
  
> 出站邮件正在发送中。
    
LOGOFF_OUTBOUND_QUEUE 
  
> 出站邮件挂起 (，即它们位于发件箱) 。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注销已成功完成。
    
## <a name="remarks"></a>备注

**IMsgStore：：StoreLogoff** 方法在注销过程中控制邮件存储和传输提供程序的交互。 调用 **StoreLogoff** 仅对仅由调用方使用的邮件存储有效。 例如，当两个客户端使用相同的邮件存储，其中一个客户端调用 **StoreLogoff** 时，邮件存储将立即释放，并且控制权将返回到调用客户端。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

保存传递给 **StoreLogoff** 的标志，在调用 [IMAPISupport：：StoreLogoffTransports](imapisupport-storelogofftransports.md) 方法时传递它们。 请勿调用 **StoreLogoffTransports，** 直到邮件存储的引用计数下降为零。 多次调用 **StoreLogoffTransports** 只会覆盖保存的标志。 
  
如果在邮件存储的引用计数达到零之前未对 **StoreLogoff** 进行调用，则设置传递到 **StoreLogoffTransports** 的 _ulFlags_ 参数中的 LOGOFF_ABORT 标志。
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)
  
[IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md)
  
[IXPLogon::FlushQueues](ixplogon-flushqueues.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

