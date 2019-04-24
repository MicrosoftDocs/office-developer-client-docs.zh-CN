---
title: IXPLogonStartMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.StartMessage
api_type:
- COM
ms.assetid: 83c349f7-dcac-4268-befe-fb2bc0cd9c50
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 00273d5572fa0c12a9501a1620db11ea087fd5d1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351595"
---
# <a name="ixplogonstartmessage"></a>IXPLogon::StartMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动从传输提供程序到 MAPI 后台处理程序的入站邮件传输。
  
```cpp
HRESULT StartMessage(
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMsgRef
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lpMessage_
  
> 实时指向具有读/写权限的邮件对象 (表示入站邮件) 的指针, 该对象由传输提供程序用来访问和操作该邮件。 此对象一直保持有效, 直到传输提供程序从对**IXPLogon:: StartMessage**的调用返回。
    
 _lpulMsgRef_
  
> 排除指向分配给邮件的引用值的指针。 MAPI 后台处理程序将此值初始化为 1, 然后再将指针返回到传输提供程序。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IXPLogon:: StartMessage**方法, 以启动从传输提供程序到 MAPI 后台处理程序的入站邮件的传输。 在传输提供程序开始使用由_lpMessage_指向的邮件之前, 它应在_lpulMsgRef_参数中存储消息引用, 以便可以调用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法, 以供潜在使用。 
  
在**StartMessage**呼叫过程中, MAPI 后台处理程序将处理在邮件传输过程中打开的对象的方法, 并且还会处理所有附件。 此处理可能需要很长时间。 在此处理过程中, 传输提供程序可以在此处理过程中频繁调用 MAPI 后台处理程序的[IMAPISupport:: SpoolerYield](imapisupport-spooleryield.md)回调函数, 以释放其他系统任务的 CPU 时间。 
  
收件人表中的传输提供程序为邮件创建的所有收件人必须包含所有必需的寻址属性。 如有必要, 提供程序可以构造自定义收件人以代表特定收件人。 但是, 如果提供程序可以生成包含详细信息的收件人条目, 则应执行此操作。 例如, 如果传输提供程序具有有关通讯簿提供程序的收件人格式的足够信息, 可以为该格式的收件人生成有效的条目标识符, 则它应生成条目标识符。
  
如果收到任何 nontransmittable 属性, 则传输提供程序不应将其存储在新邮件中。 但是, 传输提供程序应将其收到的所有传输属性存储在新邮件中。
  
如果传入邮件是传递报告或 nondelivery 报告, 并且传输提供程序无法使用[IMAPISupport:: StatusRecips](imapisupport-statusrecips.md)方法来生成来自原始邮件的报告, 则提供程序将自行在中填充邮件相应的属性。 但是, 传输提供程序无法设置邮件的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
  
若要在处理后将传入邮件保存在相应的 MAPI 邮件存储库中, 传输提供程序将调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法。 如果传输提供程序没有任何要传递给 MAPI 后台处理程序的邮件, 它可以通过从**StartMessage**调用返回, 而无需调用**SaveChanges**, 从而停止传入的邮件。
  
传输提供程序在**StartMessage**呼叫过程中打开的所有对象都应在返回之前释放。 但是, 提供程序不应释放 MAPI 假脱机程序最初在_lpMessage_参数中传递的邮件对象。 
  
如果**StartMessage**返回错误, 则会在不保存更改的情况下释放进程中的邮件, 并且该邮件将丢失。 在这种情况下, 传输提供程序应通过调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法传递 NOTIFY_CRITICAL_ERROR 标志并调用[IXPLogon::P oll](ixplogon-poll.md)方法, 以通知 MAPI 后台处理程序存在严重的错误情况。 
  
有关详细信息, 请参阅[与 MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)
  
[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)
  
[IMessage::GetRecipientTable](imessage-getrecipienttable.md)
  
[IXPLogon::Poll](ixplogon-poll.md)
  
[IXPLogon::TransportNotify](ixplogon-transportnotify.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

