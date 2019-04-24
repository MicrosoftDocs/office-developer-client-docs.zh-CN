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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326318"
---
# <a name="imapisupportpreparesubmit"></a>IMAPISupport::PrepareSubmit

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
准备邮件以提交到 MAPI 后台处理程序。
  
```cpp
HRESULT PrepareSubmit(
LPMESSAGE lpMessage,
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> 实时指向要准备的邮件的指针。
    
 _lpulFlags_
  
> [in, out]在输入时, _lpulFlags_参数是保留参数, 并且必须为零。 在输出时, _lpulFlags_必须为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功准备就绪。
    
## <a name="remarks"></a>注解

**IMAPISupport::P reparesubmit**方法是为邮件存储提供程序支持对象而实现的。 邮件存储提供程序在其[IMessage:: SubmitMessage](imessage-submitmessage.md)方法的实现中调用**PrepareSubmit** , 以准备要提交到 MAPI 后台处理程序的邮件。 
  
 **PrepareSubmit**用于处理在其**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置了 MSGFLAG_RESEND 标志的邮件。 MSGFLAG_RESEND 是为包含在初始传输失败时发送的请求的邮件而设置的。 **PrepareSubmit**确定收件人列表中的哪些收件人已成功接收邮件, 但没有。 
  
若要访问收件人列表, **PrepareSubmit**调用邮件的[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)方法。 若要检索收件人数据, **PrepareSubmit**调用收件人表的[IMAPITable:: QueryRows](imapitable-queryrows.md)方法。 对于表中的每一行, **PrepareSubmit**检查**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性并执行下列操作之一:
  
- 如果设置了 MAPI_SUBMITTED 标志, 则**PrepareSubmit**将清除该标志, 并将**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE。
    
- 如果未设置 MAPI_SUBMITTED 标志, 则**PrepareSubmit**会将**PR_RECIPIENT_TYPE**更改为 MAPI_P1 并将**PR_RESPONSIBILITY**设置为 TRUE。 
    
## <a name="notes-to-callers"></a>给调用方的说明

在调用**PrepareSubmit**之前, 请确保您已调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法, 并在_ulFlags_参数中设置 NOTIFY_READYTOSEND 标志。 在对**PrepareSubmit**的调用之前, 必须为每个会话发出**SpoolerNotify**调用一次。 **SpoolerNotify**将同步 MAPI 后台处理程序, 并确保所有需要的传输提供程序均已登录并注册其地址类型。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md)
  
[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

