---
title: IMAPISupportPrepareSubmit
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.PrepareSubmit
api_type:
- COM
ms.assetid: 467242e3-96c9-4280-9cbc-9ecfe3f279cf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f6902b45cde3e5349d69b6f35c3f8980deb031b4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775670"
---
# <a name="imapisupportpreparesubmit"></a>IMAPISupport::PrepareSubmit

  
  
**适用于**： Outlook 
  
提交到 MAPI 后台处理程序准备一条消息。
  
```cpp
HRESULT PrepareSubmit(
LPMESSAGE lpMessage,
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]指向要准备的消息的指针。
    
 _lpulFlags_
  
> [传入、 传出]在输入_lpulFlags_参数保留，必须为零。 输出， _lpulFlags_必须为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功准备好。
    
## <a name="remarks"></a>备注

消息存储提供程序支持对象的实现**IMAPISupport::PrepareSubmit**方法。 消息存储提供程序调用**PrepareSubmit**其方法的实现， [IMessage::SubmitMessage](imessage-submitmessage.md) MAPI 后台处理程序提交准备一条消息。 
  
 **PrepareSubmit**用于处理其**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_RESEND 标志的消息。 为邮件，其中包括初始传输失败时重新发送的请求设置 MSGFLAG_RESEND。 **PrepareSubmit**确定哪些收件人列表中的收件人成功收到邮件，并且其没有。 
  
若要访问的收件人列表， **PrepareSubmit**调用消息的[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法。 若要检索的收件人数据， **PrepareSubmit**调用收件人表的[IMAPITable::QueryRows](imapitable-queryrows.md)方法。 对于表中的每一行， **PrepareSubmit**检查**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性，并采用下列操作之一：
  
- 如果设置了 MAPI_SUBMITTED 标志， **PrepareSubmit**清除标志，并将**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE。
    
- 如果未设置 MAPI_SUBMITTED 标志， **PrepareSubmit** **PR_RECIPIENT_TYPE**变为 MAPI_P1，并将**PR_RESPONSIBILITY**设置为 TRUE。 
    
## <a name="notes-to-callers"></a>给调用方的说明

在调用**PrepareSubmit**之前，确保您已被调用[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法并将 NOTIFY_READYTOSEND 标志设置_ulFlags_参数中。 每次会话**PrepareSubmit**调用之前，必须在进行**SpoolerNotify**呼叫。 **SpoolerNotify**同步 MAPI 后台处理程序，并确保所有所需的传输提供程序的登录和注册其地址类型。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md)
  
[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

