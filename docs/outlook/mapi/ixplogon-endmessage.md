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
  
> 实时在之前调用[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md)方法时获取的邮件特定的引用值。 
    
 _lpulFlags_
  
> 排除标志的位掩码, 用于指示 MAPI 后台处理程序对邮件所做的操作。 如果未设置任何标志, 则邮件已发送。 可以设置以下标志:
    
END_DONT_RESEND 
  
> 现在, 传输提供程序包含此邮件所需的所有信息。 当传输提供程序需要更多信息或发送邮件时, 它会通过调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法和 NOTIFY_SENTDEFERRED 标志并传递邮件的条目标识符, 来通知 MAPI 后台处理程序。 
    
END_RESEND_LATER 
  
> 由于原因不是错误条件, 传输提供程序当前无法在当前时间发送邮件。 稍后应再次调用传输提供程序以发送邮件。
    
END_RESEND_NOW 
  
> 传输提供程序需要在[IMessage:: SubmitMessage](imessage-submitmessage.md)方法调用中重新启动传递给它的邮件。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>说明

MAPI 后台处理程序在提供扩展传递或 nondelivery 信息的处理过程完成后, 调用**IXPLogon:: EndMessage**方法。 
  
此调用返回后, _ulMsgRef_参数中的值不再对此邮件有效。 传输提供程序可以在以后的邮件中重复使用相同的值。 
  
传输提供程序在邮件传输过程中打开的所有对象都应在**EndMessage**调用返回之前发布, 但 MAPI 后台处理程序传递给传输提供程序的 message 对象除外。 在**EndMessage**调用之后, MAPI 后台处理程序传递的邮件对象无效。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

