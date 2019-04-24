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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348739"
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
  
> [in, out]从邮件存储控制注销的标志的位掩码。 在输入时, 此参数设置的所有标志都是相互排斥的;呼叫者必须为每个呼叫指定一个标志。 以下标志对输入有效:
    
LOGOFF_ABORT 
  
> 在注销之前, 应停止此邮件存储的任何传输提供程序活动。 停止活动后, 控件将返回到调用方。 如果发生任何传输提供程序活动, 则不会发生注销, 且在 MAPI 后台处理程序或传输提供程序的行为中不会发生任何变化。 如果传输提供程序活动处于空闲状态, MAPI 后台处理程序将释放该存储区。 
    
LOGOFF_NO_WAIT 
  
> 在关闭之前, 邮件存储不应等待传输提供程序中的邮件。 发送已准备好发送的出站邮件。 如果此存储区包含默认收件箱, 则接收任何进程内邮件, 然后禁用进一步的接收。 所有活动完成后, MAPI 后台处理程序将释放该存储, 并立即将控制权返回给呼叫者。 
    
LOGOFF_ORDERLY 
  
> 在关闭之前, 邮件存储不应等待传输提供程序中的信息。 当前正在处理的邮件已完成, 但不处理新邮件。 所有活动完成后, MAPI 后台处理程序将释放该存储, 并立即将控制返回到存储提供程序。 
    
LOGOFF_PURGE 
  
> 注销的工作方式应与设置 LOGOFF_NO_WAIT 标志相同, 但应调用适当的传输提供程序的[IXPLogon:: FlushQueues](ixplogon-flushqueues.md)或[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法。 完成后, LOGOFF_PURGE 标志将控制权返回给调用方。 
    
LOGOFF_QUIET 
  
> 如果发生任何传输提供程序活动, 则不应发生注销。
    
    The following flags are valid on output:
    
LOGOFF_INBOUND 
  
> 入站邮件当前正在到达。
    
LOGOFF_OUTBOUND 
  
> 出站邮件正处于发送过程中。
    
LOGOFF_OUTBOUND_QUEUE 
  
> 出站邮件挂起 (即它们位于 "发件箱" 中)。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功完成注销。
    
## <a name="remarks"></a>注解

**IMsgStore:: StoreLogoff**方法 exerts 控制邮件存储和传输提供程序在注销过程中的交互。 调用**StoreLogoff**仅对仅由呼叫者使用的邮件存储区有效。 例如, 当两个客户端使用相同的邮件存储库, 并且其中一个调用**StoreLogoff**时, 邮件存储将立即发布, 并将控制权返回给呼叫客户端。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

保存传递给**StoreLogoff**的标志, 并在调用[IMAPISupport:: StoreLogoffTransports](imapisupport-storelogofftransports.md)方法时传递这些标志。 在邮件存储区的引用计数降至0时, 不要调用**StoreLogoffTransports** 。 对**StoreLogoffTransports**的多个调用只是覆盖已保存的标志。 
  
如果在邮件存储区的引用计数达到零之前未对**StoreLogoff**进行任何调用, 请在传递给**StoreLogoffTransports**的_ulFlags_参数中设置 LOGOFF_ABORT 标志。
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)
  
[IMAPISupport::StoreLogoffTransports](imapisupport-storelogofftransports.md)
  
[IXPLogon::FlushQueues](ixplogon-flushqueues.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

