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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 738eb346ec5388cbd94b32598236ef2ca05740f3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425734"
---
# <a name="imapisupportpreparesubmit"></a>IMAPISupport::PrepareSubmit

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
准备消息以提交到 MAPI 后台处理程序。
  
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
  
> [in， out]输入时  _，保留 lpulFlags_ 参数，并且必须为零。 在输出时  _，lpulFlags_ 必须为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功准备。
    
## <a name="remarks"></a>备注

**IMAPISupport：:P repareSubmit** 方法为邮件存储提供程序支持对象实现。 邮件存储提供程序在 [IMessage：：SubmitMessage](imessage-submitmessage.md)方法的实现中调用 **PrepareSubmit，** 以准备邮件以提交到 MAPI 后台处理程序。 
  
 **PrepareSubmit** 用于处理在 [PidTagMessageFlags](pidtagmessageflags-canonical-property.md) PR_MESSAGE_FLAGS (属性中设置了 **MSGFLAG_RESEND** 标志) 的邮件。 MSGFLAG_RESEND包括初始传输失败时要重新发送的请求的邮件，则设置此设置。 **PrepareSubmit** 确定收件人列表中的哪些收件人已成功收到邮件，哪些收件人未收到邮件。 
  
若要访问收件人列表 **，PrepareSubmit** 将调用邮件的 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 方法。 若要检索收件人数据 **，PrepareSubmit** 将调用收件人表的 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法。 对于表中的每一行 **，PrepareSubmit** 将检查PR_RECIPIENT_TYPE ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性，并执行以下操作之一：
  
- 如果 **MAPI_SUBMITTED，PrepareSubmit** 将清除该标志，PR_RESPONSIBILITY ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 设置为 FALSE。 
    
- 如果未设置MAPI_SUBMITTED，**则 PrepareSubmit****更改PR_RECIPIENT_TYPE** 设置为 **MAPI_P1，PR_RESPONSIBILITY** 设置为 TRUE。 
    
## <a name="notes-to-callers"></a>给调用方的说明

在调用 **PrepareSubmit** 之前，请确保已调用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法，并设置  _ulFlags_ 参数中的 NOTIFY_READYTOSEND 标志。 在调用 **PrepareSubmit** 之前，必须每个会话进行一次 **SpoolerNotify** 调用。 **SpoolerNotify** 同步 MAPI 后台处理程序，并确保已登录所有所需的传输提供程序并注册其地址类型。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md)
  
[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

