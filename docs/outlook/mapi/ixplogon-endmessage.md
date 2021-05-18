---
title: IXPLogonEndMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.EndMessage
api_type:
- COM
ms.assetid: bb29e6a0-7a92-46eb-bbeb-6f2df6ac6d21
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 03eccfe27c6f93e42ee01a34fbf5df766c145cf1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414156"
---
# <a name="ixplogonendmessage"></a>IXPLogon::EndMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知传输提供程序 MAPI 后台处理程序已完成对出站邮件的处理。
  
```cpp
HRESULT EndMessage(
  ULONG ulMsgRef,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _ulMsgRef_
  
> [in]在之前对 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md) 方法的调用中获取的特定于邮件的引用值。 
    
 _lpulFlags_
  
> [out]指示 MAPI 后台处理程序应该对消息执行哪些操作的标志的位掩码。 如果未设置标志，则邮件已发送。 可以设置以下标志：
    
END_DONT_RESEND 
  
> 传输提供程序目前包含其需要有关此邮件的所有信息。 当传输提供程序需要更多信息或发送消息时，它将通过调用具有 NOTIFY_SENTDEFERRED 标志的 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法并传递邮件的条目标识符来通知 MAPI 后台处理程序。 
    
END_RESEND_LATER 
  
> 由于非错误条件的原因，传输提供程序当前不发送邮件。 稍后应再次调用传输提供程序以发送邮件。
    
END_RESEND_NOW 
  
> 传输提供程序需要重新启动 [在 IMessage：：SubmitMessage](imessage-submitmessage.md) 方法调用中传递给它的邮件。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
## <a name="remarks"></a>备注

MAPI 后台处理程序在完成提供扩展传递或非传递信息所涉及的处理后调用 **IXPLogon：：EndMessage** 方法。 
  
一旦此调用返回  _，ulMsgRef_ 参数中的值将不再对此消息有效。 传输提供程序可以在将来的邮件上重用相同的值。 
  
传输提供程序在传输邮件期间打开的所有对象都应在 **EndMessage** 调用返回之前释放，MAPI 后台处理程序传递给传输提供程序的邮件对象除外。 MAPI 后台处理程序传递的消息对象在 **EndMessage** 调用后无效。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

