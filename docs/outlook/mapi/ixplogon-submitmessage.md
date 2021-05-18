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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ae124cb94cff5be0a655386d31f1bf2c82f66a85
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423319"
---
# <a name="ixplogonsubmitmessage"></a>IXPLogon::SubmitMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示 MAPI 后台处理程序具有要传递的传输提供程序的邮件。
  
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
  
> [in]控制邮件提交方式的标志位掩码。 可以设置以下标志：
    
BEGIN_DEFERRED 
  
> MAPI 后台处理程序使用之前延迟的邮件调用传输提供程序。 邮件的条目标识符与延迟时相同。 通过使用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法（带 NOTIFY_SENTDEFERRED 标志）将邮件传递回 MAPI 后台处理程序，延迟了消息。 
    
 _lpMessage_
  
> [in]指向邮件对象 (表示要传递的邮件) 具有读/写权限的邮件对象，传输提供程序使用该指针访问和处理该邮件。 在传输提供程序从对 [IXPLogon：：EndMessage](ixplogon-endmessage.md) 方法的后续调用返回之前，此对象一直有效。 
    
 _lpulMsgRef_
  
> [out]指向一个变量的指针，传输提供程序在此变量中返回分配给此邮件的引用值。 MAPI 后台处理程序在此消息的后续调用中传递此引用值。 MAPI 后台处理程序将该值初始化为 0，然后再将该值返回到传输提供程序。
    
 _lpulReturnParm_
  
> [out]指向对应于 **SubmitMessage** 返回的错误MAPI_E_WAIT或MAPI_E_NETWORK_ERROR返回的变量的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
MAPI_E_BUSY 
  
> 传输提供程序无法处理邮件，因为它正在执行另一个操作。 提供程序应该使用此返回值来指示未进行处理，并且 MAPI 后台处理程序不应调用 **EndMessage**。 MAPI 后台处理程序稍后将再次尝试 **SubmitMessage** 调用。 
    
MAPI_E_CANCEL 
  
> 尽管传输提供程序请求 MAPI 后台处理程序在之前的 **SpoolerNotify** 调用上重新提交邮件，但之后条件已更改，不应重新发送该邮件。 MAPI 后台处理程序将继续处理其他操作。 
    
MAPI_E_NETWORK_ERROR 
  
> 网络错误阻止成功完成操作。 _lpulReturnParm_ 参数应设置为 MAPI 后台处理程序重新提交邮件之前经过的秒数。 
    
MAPI_E_NOT_ME 
  
> 传输提供程序无法处理此邮件。 MAPI 后台处理程序应尝试查找它的另一个传输提供程序。 提供程序应该使用此返回值来指示未进行处理，并且 MAPI 后台处理程序不应调用 **EndMessage**。
    
MAPI_E_WAIT 
  
> 临时问题阻止传输提供程序处理邮件。 _lpulReturnParm_ 参数应设置为 MAPI 后台处理程序重新提交邮件之前经过的秒数。 
    
## <a name="remarks"></a>备注

当 MAPI 后台处理程序有消息供传输提供程序传递时，它将调用 **IXPLogon：：SubmitMessage** 方法。 邮件使用  _lpMessage_ 参数传递给传输提供程序。 
  
如果提供程序已准备好接受邮件，它应通过使用  _lpulMsgRef_ 参数返回一个引用值，处理传递的对象，并返回 (值S_OK) 。 如果提供程序未准备好处理传输，它应返回一个错误值，并且（可选）在  _lpulReturnParm_ 中返回另一个 MAPI 返回值，以指示 MAPI 后台处理程序在重新提交邮件之前应等待多久。 
  
传输提供程序的此方法实现可以执行以下操作：
  
- 将邮件放入内部队列以等待传输，可能会将邮件复制到本地存储并返回。
    
- 尝试执行实际传输，在传输完成时返回成功或不成功。
    
- 确定在检查涉及的资源后是否发送邮件。 在这种情况下，如果资源是免费的，则提供程序可以锁定资源、准备消息并提交它。 如果资源繁忙，提供程序可以准备消息并延迟到以后发送。
    
邮件传输的首选技术取决于传输提供程序和与系统资源竞争的预期进程数。 
  
在 **SubmitMessage** 调用期间，传输提供程序控制从邮件对象传输邮件数据。 但是，传输提供程序应为邮件分配一个引用值，在传输数据之前，它会在  _lpulMsgRef_ 中向该邮件返回一个指针。 它这样做是因为，在过程中的任何时间点，MAPI 后台处理程序都可以调用 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) 方法，同时将 NOTIFY_CANCEL_MESSAGE 标志设置为向提供程序发出信号，指示它应释放任何打开的对象并停止消息传输。 
  
传输提供程序不应发送邮件的任何不可传递的属性。 当找到此类属性时，它应继续处理下一个属性。 提供商应尽一切努力不将MAPI_P1信息作为传输的邮件内容的一部分显示;提供程序应仅出于寻址目的使用此收件人信息。 MAPI_P1收件人是内部生成的用于重新发送邮件的收件人;它们不应进行传输。 请改为使用其他收件人传输收件人信息。 这种安排的目的是允许重新发送收件人查看与原始收件人完全相同的收件人表。
  
在 **SubmitMessage** 调用期间，MAPI 后台处理程序处理在邮件传输过程中打开的对象的方法，并处理任何附件。 此处理可能需要很长时间。 传输提供程序可以在此处理过程中频繁调用 MAPI 后台处理程序的 [IMAPISupport：：SpoolerYield](imapisupport-spooleryield.md) 方法，以释放其他系统任务的 CPU 时间。 
  
所有邮件收件人都显示在 MAPI 后台处理程序最初传递的邮件的收件人表中。 传输提供程序应仅处理可处理的收件人（基于条目标识符、地址类型或两者）以及尚未将 **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE 的收件人。 如果 **PR_RESPONSIBILITY** 设置为 TRUE，则另一个传输提供程序已处理该收件人。 当提供程序完成收件人的充分处理以确定其是否可以处理该收件人的邮件时，它应在传递的邮件中将收件人的 **PR_RESPONSIBILITY** 属性设置为 TRUE。 通常，提供程序在邮件传递完成后做出此决定。 
  
通常，在传输提供程序完成邮件数据的传输之前，不会从 **SubmitMessage** 调用返回。 如果未返回错误，则从 MAPI 后台处理程序到提供程序的下一个调用是调用 [IXPLogon：：EndMessage](ixplogon-endmessage.md) 方法。 
  
如果 **SubmitMessage** 返回错误，MAPI 后台处理程序将在不保存更改的情况下释放正在处理的消息。 如果传输提供程序要求保存邮件更改，则必须在返回之前对邮件调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。 
  
如果由于传输问题而发生错误，MAPI 后台处理程序会保留邮件，但会延迟根据  _lpulReturnParm_ 中返回的值将邮件重新提交到传输提供程序。 如果 **SubmitMessage** 返回的值是 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR。 如果发生严重错误情况，传输提供程序必须调用具有"错误"标志的 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) NOTIFY_CRITICAL_ERROR方法。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)
  
[IXPLogon::EndMessage](ixplogon-endmessage.md)
  
[IXPLogon::TransportNotify](ixplogon-transportnotify.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

