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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2ac8fb6f4e56b6f086e6061c227120cd49fc621a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775884"
---
# <a name="imsgstorestorelogoff"></a>IMsgStore::StoreLogoff

  
  
**适用于**： Outlook 
  
允许的邮件存储的有序注销。
  
```cpp
HRESULT StoreLogoff(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [传入、 传出]位掩码的标志控制消息存储中的注销。 在输入所有标志设置为此参数相互都排斥;呼叫者必须指定每次呼叫只有一个标志。 以下标志是上输入有效的：
    
LOGOFF_ABORT 
  
> 在注销之前，应停止此消息存储的任何传输提供程序活动。 停止活动后，将返回到呼叫者控制权。 如果任何传输提供程序活动正在进行，注销，不会发生，就会发生任何更改 MAPI 后台处理程序或传输提供程序的行为。 传输提供程序活动处于空闲状态，如果 MAPI 后台处理程序释放存储。 
    
LOGOFF_NO_WAIT 
  
> 消息存储不应等待来自传输提供程序在关闭之前的邮件。 已准备好进行发送出站邮件发送。 如果将此存储区包含默认收件箱，收到任何进程内消息，然后禁用进一步接收。 所有活动完成后，MAPI 后台处理程序释放存储，并控制立即返回到呼叫者。 
    
LOGOFF_ORDERLY 
  
> 消息存储不应等待关闭前的传输提供程序的信息。 当前正在处理的消息都已完成，但没有新邮件处理。 所有活动完成后，MAPI 后台处理程序释放存储，并控制立即返回到存储提供程序。 
    
LOGOFF_PURGE 
  
> 注销应工作相同设置 LOGOFF_NO_WAIT 标志，但应调用[IXPLogon::FlushQueues](ixplogon-flushqueues.md)或[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法的合适的传输提供程序。 LOGOFF_PURGE 标志完成后返回到呼叫者的控件。 
    
LOGOFF_QUIET 
  
> 如果任何传输提供程序活动正在进行，不应发生注销。
    
    The following flags are valid on output:
    
LOGOFF_INBOUND 
  
> 当前正在传入入站的邮件。
    
LOGOFF_OUTBOUND 
  
> 发送正在出站邮件。
    
LOGOFF_OUTBOUND_QUEUE 
  
> 出站邮件处于挂起状态 （即，它们是在发件箱）。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功完成注销。
    
## <a name="remarks"></a>说明

**IMsgStore::StoreLogoff**方法 exerts 控件通过交互的邮件存储并注销过程中传输提供程序。 调用**StoreLogoff**是仅供正在使用仅的呼叫者的消息存储。 例如，当两个客户端使用相同的消息存储，并且其中之一调用**StoreLogoff**，立即发布的消息存储和控制返回到调用客户端。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

保存传递给**StoreLogoff**的标志，并将它们传递调用[IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md)方法时。 不要调用**StoreLogoffTransports** ，直到消息存储库的引用计数为 0。 多个调用**StoreLogoffTransports**只需覆盖已保存的标志。 
  
如果没有呼叫做**StoreLogoff**之前邮件存储的引用计数为零时，传递给**StoreLogoffTransports** _ulFlags_参数中设置 LOGOFF_ABORT 标志。
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)
  
[IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md)
  
[IXPLogon::FlushQueues](ixplogon-flushqueues.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

