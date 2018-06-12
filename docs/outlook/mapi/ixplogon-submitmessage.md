---
title: IXPLogonSubmitMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.SubmitMessage
api_type:
- COM
ms.assetid: a261ba0d-cb56-4935-b745-1d4bbd0b8b9d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8a0b10596bdfdc1ea33f6d170ee1e021193d3788
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776138"
---
# <a name="ixplogonsubmitmessage"></a>IXPLogon::SubmitMessage

  
  
**适用于**： Outlook 
  
指示 MAPI 后台处理程序都有要提供的传输提供程序的消息。
  
```cpp
HRESULT SubmitMessage(
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMsgRef,
  ULONG FAR * lpulReturnParm
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控制如何提交邮件。 可以设置以下标记：
    
BEGIN_DEFERRED 
  
> MAPI 后台处理程序调用以前推迟一条消息的传输提供程序。 邮件的项标识符时相同它已被延迟。 邮件已被延迟通过将其条目标识符传递回 MAPI 后台处理程序[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法使用 NOTIFY_SENTDEFERRED 标志。 
    
 _lpMessage_
  
> [in]一个指向 message 对象 （表示要发送的消息） 具有读/写权限，传输提供程序使用来访问和处理该邮件。 传输提供程序返回从后续调用[IXPLogon::EndMessage](ixplogon-endmessage.md)方法后，该对象保持有效之前。 
    
 _lpulMsgRef_
  
> [输出]指向中传输提供程序返回其分配给此消息的参考值变量的指针。 MAPI 后台处理程序中后续呼叫，此消息传递参考该值。 MAPI 后台处理程序返回到传输提供程序之前初始化为 0 的值。
    
 _lpulReturnParm_
  
> [输出]指向由**SubmitMessage**返回的 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR 错误值对应一个变量的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
MAPI_E_BUSY 
  
> 传输提供程序无法处理邮件，因为它执行其他操作。 提供程序应使用此返回的值，以指示不会处理出现和 MAPI 后台处理程序不应调用**EndMessage**。 MAPI 后台处理程序将稍后再试**SubmitMessage**呼叫。 
    
MAPI_E_CANCEL 
  
> 尽管传输提供程序请求 MAPI 后台处理程序重新提交邮件在以前**SpoolerNotify**呼叫，此后更改条件，并且应不重新发送邮件。 MAPI 后台处理程序将继续处理其他内容。 
    
MAPI_E_NETWORK_ERROR 
  
> 网络错误阻止操作成功的完成。 _LpulReturnParm_参数应设置为的 MAPI 后台处理程序重新提交邮件之前所经过的秒数。 
    
MAPI_E_NOT_ME 
  
> 传输提供程序无法处理此消息。 MAPI 后台处理程序应尝试查找另一个传输提供程序。 提供程序应使用此返回的值，以指示不会处理出现和 MAPI 后台处理程序不应调用**EndMessage**。
    
MAPI_E_WAIT 
  
> 暂时出现问题阻止传输提供程序处理邮件。 _LpulReturnParm_参数应设置为的 MAPI 后台处理程序重新提交邮件之前所经过的秒数。 
    
## <a name="remarks"></a>备注

MAPI 后台处理程序调用**IXPLogon::SubmitMessage**方法时要提供的传输提供程序的消息。 通过使用_lpMessage_参数情况下，邮件传递到传输提供程序。 
  
如果已准备好接受消息提供程序，它应通过_lpulMsgRef_参数，过程传递的对象，返回的引用值并返回相应的值 (通常 S_OK)。 如果不准备处理传输提供程序，它应返回错误值，并 （可选），另一个 MAPI 返回中_lpulReturnParm_以指示 MAPI 后台处理程序重新提交邮件之前应等待的时间长度值。 
  
传输提供程序实现此方法可以执行以下操作：
  
- 邮件置于内部队列等待传输，原因可能将邮件复制到本地存储，并返回。
    
- 尝试执行的实际传输和返回传输完成后，成功或失败。
    
- 确定是否检查所涉及的资源后发送邮件。 在这种情况下，如果资源是免费的提供程序可以锁定资源、 准备邮件，并将其提交。 如果资源正忙，提供程序可以准备邮件并推迟到以后某个时间发送。
    
邮件传输的首选的方法取决于传输提供程序和预期的数量的流程争夺系统资源。 
  
**SubmitMessage**呼叫期间，传输提供程序控制传输的消息数据从 message 对象。 但是，传输提供程序应将引用值分配给邮件，向其返回一个指向在_lpulMsgRef_之前传输数据。 它因此因为可以在任何点在过程中，调用 MAPI 后台处理程序将[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法与 NOTIFY_CANCEL_MESSAGE 标志设置为信号提供程序，它应释放任何打开的对象并停止邮件传输。 
  
传输提供程序不应发送消息的任何 nontransmittable 属性。 如果找到此类属性，它应继续处理的下一个属性。 提供程序应尽力不传输的消息内容; 的一部分显示 MAPI_P1 收件人信息提供程序应仅对寻址目的使用此收件人的信息。 MAPI_P1 收件人是内部生成的用于重新发送消息;他们应不会传输。 相反，使用其他收件人的传输收件人的信息。 这种排列的用途是允许重新发送收件人为原始收件人看到完全相同的收件人表。
  
**SubmitMessage**调用，过程中 MAPI 后台处理程序处理的邮件传输过程中打开的对象的方法以及处理任何附件。 此处理花费很长时间。 传输提供程序可以发布的其他系统任务的 CPU 时间此处理过程中经常调用了的 MAPI 后台处理程序的[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)方法。 
  
所有收件人都都能看到收件人的 MAPI 后台处理程序最初传递的消息表中。 传输提供程序应处理只有它可以处理这些收件人 — 基于条目标识符、 地址类型，或同时 — 和尚未其**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE。 如果**PR_RESPONSIBILITY**已设置为 TRUE，另一个传输提供程序已经处理该收件人。 提供程序完成后足够处理的以确定是否可以为该收件人处理邮件的收件人，它应将该收件人**PR_RESPONSIBILITY**属性设置为 TRUE 传递的消息。 通常，提供程序进行此项确定邮件传递完成之后。 
  
通常，传输提供程序不返回**SubmitMessage**调用直到它完成传输邮件数据。 如果不返回任何错误，来自 MAPI 后台处理程序向提供程序的下一个呼叫是对[IXPLogon::EndMessage](ixplogon-endmessage.md)方法的调用。 
  
如果**SubmitMessage**将返回错误，MAPI 后台处理程序将释放而不保存更改的过程中的消息。 如果传输提供程序所需的消息将更改保存，它必须返回之前对邮件调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。 
  
由于传输问题出现的错误，显示 MAPI 后台处理程序保持在原有的邮件，但不是延迟重新提交的邮件传输提供程序基于_lpulReturnParm_中返回的值。 如果从**SubmitMessage**其返回值是 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR，传输提供程序必须填写该值。 如果出现严重错误情况，传输提供程序必须调用带 NOTIFY_CRITICAL_ERROR 标志的[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)
  
[IXPLogon::EndMessage](ixplogon-endmessage.md)
  
[IXPLogon::TransportNotify](ixplogon-transportnotify.md)
  
[IXPLogon: IUnknown](ixplogoniunknown.md)

