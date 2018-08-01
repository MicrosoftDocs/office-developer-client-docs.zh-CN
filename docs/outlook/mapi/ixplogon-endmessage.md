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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7f81a0c3c9a9ad0a9bcef5c5685aa5b343237f19
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776114"
---
# <a name="ixplogonendmessage"></a>IXPLogon::EndMessage

  
  
**适用于**： Outlook 
  
通知传输提供程序 MAPI 后台处理程序完成对出站邮件及其处理。
  
```cpp
HRESULT EndMessage(
  ULONG ulMsgRef,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _ulMsgRef_
  
> [in]在以前的[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法调用中获得一个特定的消息参考值。 
    
 _lpulFlags_
  
> [输出]位掩码的标志，指示 MAPI 后台处理程序向它应为邮件执行的操作。 如果未设置标志，已发送邮件。 可以设置以下标志：
    
END_DONT_RESEND 
  
> 传输提供程序具有现在需要有关此消息的所有信息。 传输提供程序要求的详细信息时，或者它已发送邮件时，它会通知 MAPI 后台处理程序，通过调用带 NOTIFY_SENTDEFERRED 标志的[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法和传递消息的项标识符。 
    
END_RESEND_LATER 
  
> 传输提供程序不条件时发生错误的原因的当前时间在不发送邮件。 传输提供程序应调用再次更高版本来发送邮件。
    
END_RESEND_NOW 
  
> 传输提供程序需要重新启动[IMessage::SubmitMessage](imessage-submitmessage.md)方法调用中传递给它的消息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>说明

完成处理参与提供扩展的传递或原件信息后，MAPI 后台处理程序调用**IXPLogon::EndMessage**方法。 
  
一旦返回此呼叫，将不再有效此消息的_ulMsgRef_参数中的值。 传输提供程序可以重用将来的消息的相同值。 
  
**EndMessage**呼叫返回，除外 MAPI 后台处理程序将传递到传输提供程序的消息对象之前，应释放的邮件传输过程中打开传输提供程序的所有对象。 Message 对象传递的 MAPI 后台处理程序无效**EndMessage**调用后。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
  
[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

