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
  
指示 MAPI 后台处理程序有要传递的传输提供程序的消息。
  
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
  
> 实时用于控制如何提交邮件的标志的位掩码。 可以设置以下标志:
    
BEGIN_DEFERRED 
  
> MAPI 后台处理程序正在使用以前延迟的邮件调用传输提供程序。 邮件的条目标识符与延迟时相同。 通过使用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法和 NOTIFY_SENTDEFERRED 标志将其条目标识符传递回 MAPI 后台处理程序, 从而推迟了邮件。 
    
 _lpMessage_
  
> 实时一个指针, 指向具有读/写权限的邮件对象 (表示要传递的邮件), 传输提供程序使用该对象来访问和操作该邮件。 此对象将一直保持有效, 直到传输提供程序从对[IXPLogon:: EndMessage](ixplogon-endmessage.md)方法的后续调用返回。 
    
 _lpulMsgRef_
  
> 排除一个指针, 指向传输提供程序在其中返回其分配给此邮件的引用值的变量。 MAPI 后台处理程序在此邮件的后续调用中传递此引用值。 MAPI 后台处理程序将此值初始化为 0, 然后再将其返回到传输提供程序。
    
 _lpulReturnParm_
  
> 排除指向与**SubmitMessage**返回的 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR 错误值相对应的变量的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
MAPI_E_BUSY 
  
> 传输提供程序无法处理邮件, 因为它正在执行其他操作。 提供程序应使用此返回值指示未发生任何处理, MAPI 后台处理程序不应调用**EndMessage**。 MAPI 后台处理程序将稍后再次尝试**SubmitMessage**调用。 
    
MAPI_E_CANCEL 
  
> 尽管传输提供程序请求 MAPI 后台处理程序重新提交以前的**SpoolerNotify**调用的邮件, 但条件已更改, 不应重发邮件。 MAPI 后台处理程序将继续处理其他内容。 
    
MAPI_E_NETWORK_ERROR 
  
> 网络错误阻止操作成功完成。 应将_lpulReturnParm_参数设置为 MAPI 后台处理程序重新提交邮件之前所经过的秒数。 
    
MAPI_E_NOT_ME 
  
> 传输提供程序无法处理此邮件。 MAPI 后台处理程序应尝试为其查找其他传输提供程序。 提供程序应使用此返回值指示未发生任何处理, MAPI 后台处理程序不应调用**EndMessage**。
    
MAPI_E_WAIT 
  
> 临时问题会阻止传输提供程序处理邮件。 应将_lpulReturnParm_参数设置为 MAPI 后台处理程序重新提交邮件之前所经过的秒数。 
    
## <a name="remarks"></a>说明

MAPI 后台处理程序调用**IXPLogon:: SubmitMessage**方法, 以使传输提供程序能够传递邮件。 通过使用_lpMessage_参数将邮件传递给传输提供程序。 
  
如果提供程序准备好接受邮件, 则应使用_lpulMsgRef_参数返回一个引用值, 处理传递的对象, 然后返回适当的值 (通常为 S_OK)。 如果提供程序未准备好处理传输, 它应返回一个错误值, 也可以返回_lpulReturnParm_中的另一个 MAPI 返回值, 以指示 mapi 后台处理程序在重新提交邮件之前应等待的时间。 
  
此方法的传输提供程序的实现可以执行以下操作:
  
- 将邮件放入内部队列以等待传输, 可能将邮件复制到本地存储, 并返回。
    
- 尝试在传输完成 (无论成功还是失败) 时执行实际传输并返回。
    
- 确定在检查所涉及的资源后是否发送邮件。 在这种情况下, 如果资源是免费的, 则提供程序可以锁定资源、准备邮件并提交邮件。 如果资源处于忙碌状态, 则提供程序可以准备邮件并推迟发送到稍后的时间。
    
邮件传输的首选技术取决于传输提供程序和争用系统资源的预期进程数。 
  
在**SubmitMessage**呼叫过程中, 传输提供程序控制邮件对象的邮件数据传输。 但是, 传输提供程序应在_lpulMsgRef_中向其返回指针的消息分配一个引用值, 然后再传输数据。 这是因为在过程中的任何时刻, MAPI 后台处理程序都可以调用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法并设置 NOTIFY_CANCEL_MESSAGE 标志, 以向提供程序发出通知, 告知其应释放任何打开的对象并停止邮件传输。 
  
传输提供程序不应发送邮件的任何 nontransmittable 属性。 当找到此类属性时, 它应继续处理下一个属性。 提供程序应尽一切努力将 MAPI_P1 收件人信息显示为传输的邮件内容的一部分;提供程序应仅出于寻址目的而使用此收件人信息。 MAPI_P1 收件人是内部生成的用于重新发送邮件的收件人;不应传输它们。 而是使用其他收件人传输收件人信息。 这种安排的目的是允许重发收件人查看与原始收件人完全相同的收件人表。
  
在**SubmitMessage**呼叫过程中, MAPI 后台处理程序将处理在邮件传输过程中打开的对象的方法, 并处理所有附件。 此处理可能需要很长时间。 在此处理过程中, 传输提供程序可以为 MAPI 后台处理程序调用[IMAPISupport:: SpoolerYield](imapisupport-spooleryield.md)方法, 以在其他系统任务中释放 CPU 时间。 
  
MAPI 后台处理程序最初传递的邮件的收件人表中显示所有邮件收件人。 传输提供程序应仅处理其可处理的收件人 (基于条目标识符、地址类型或两者), 且尚未将其**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE。 如果**PR_RESPONSIBILITY**已设置为 TRUE, 则另一个传输提供程序已处理该收件人。 当提供程序完成对收件人的足够处理以确定是否可以处理该收件人的邮件时, 应将该收件人的**PR_RESPONSIBILITY**属性设置为 TRUE, 并在传递的邮件中。 通常, 提供程序在邮件传递完成后进行此确定。 
  
通常情况下, 传输提供程序在完成邮件数据的传输之前不会从**SubmitMessage**调用返回。 如果没有返回错误, 则从 MAPI 后台处理程序到提供程序的下一个调用是对[IXPLogon:: EndMessage](ixplogon-endmessage.md)方法的调用。 
  
如果**SubmitMessage**返回错误, MAPI 后台处理程序将在不保存更改的情况下释放邮件。 如果传输提供程序要求保存邮件更改, 则必须在返回前对邮件调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法。 
  
如果传输问题导致出现错误, MAPI 后台处理程序将保留邮件, 但会根据_lpulReturnParm_中返回的值, 延迟将邮件重新提交到传输提供程序。 如果**SubmitMessage**的返回值是 MAPI_E_WAIT 或 MAPI_E_NETWORK_ERROR, 则传输提供程序必须填写该值。 如果发生严重错误, 则传输提供程序必须使用 NOTIFY_CRITICAL_ERROR 标记调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)
  
[IXPLogon::EndMessage](ixplogon-endmessage.md)
  
[IXPLogon::TransportNotify](ixplogon-transportnotify.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

