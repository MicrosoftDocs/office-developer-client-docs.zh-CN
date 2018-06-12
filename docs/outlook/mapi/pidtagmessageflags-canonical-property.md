---
title: PidTagMessageFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageFlags
api_type:
- HeaderDef
ms.assetid: 7561112b-ca72-4c49-a8a0-cc1879a4e151
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: f2e565dc8137edee441643a5d02a154f78737099
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777859"
---
# <a name="pidtagmessageflags-canonical-property"></a>PidTagMessageFlags 规范属性

  
  
**适用于**： Outlook 
  
包含指示的原点和消息的当前状态标志的位掩码。 
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_MESSAGE_FLAGS  <br/> |
|标识符:  <br/> |0x0E07  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性是传输的同时发送和接收结束，具体取决于客户端应用程序或存储提供程序所涉及的不同值公开 nontransmittable message 属性。 此属性由客户端或消息存储提供程序创建和保存第一次，然后定期更新消息存储提供程序、 传输提供程序，和 MAPI 后台处理程序处理邮件消息时，其状态初始化更改。 
  
此属性存在一条消息，before 和 after 提交，和上收到的邮件的所有副本。 尽管不收件人属性，它向已公开不同根据是否已读取或修改的收件人的每个收件人。 
  
此属性，可以设置一个或多个以下标志：
  
MSGFLAG_ASSOCIATED 
  
> 邮件是文件夹的关联的邮件。 在客户端或提供程序具有到此标志的只读访问权限。 关联的消息，不保留读/未读状态的情况下，将忽略 MSGFLAG_READ 标志。 
    
MSGFLAG_FROMME 
  
> 消息的用户发送已接收邮件的邮件用户。 在客户端或提供程序具有读/写访问此标志直到首次[IMAPIProp::SaveChanges](imapiprop-savechanges.md)调用和只读此后。 此标志是为了由传输提供程序设置。 
    
MSGFLAG_HASATTACH 
  
> 邮件已至少一个附件。 此标志对应于消息的**PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md)) 属性。 客户端具有只读访问权限此标志。 
    
MSGFLAG_NRN_PENDING 
  
> Nonread 的报告需要发送的邮件。 在客户端或提供程序具有到此标志的只读访问权限。 
    
MSGFLAG_ORIGIN_INTERNET 
  
> 传入消息到达通过 Internet。 它是组织外部，也可以从受信任的源无法考虑网关。 客户端应向用户显示相应的消息。 传输提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_ORIGIN_MISC_EXT 
  
> 传入消息到达通过 X.400 或 Internet 外部链接。 它是组织外部，也可以从受信任的源无法考虑网关。 客户端应向用户显示相应的消息。 传输提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_ORIGIN_X400 
  
> 传入消息到达通过 X.400 链接。 它是组织外部，也可以从受信任的源无法考虑网关。 客户端应向用户显示相应的消息。 传输提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_READ 
  
> 邮件标记为已读。 这可能会调用随时[IMessage::SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)的结果。 客户端还可以通过之前邮件已保存第一次调用一条消息**IMAPIProp::SetProps**方法设置此标志。 如果设置了**MSGFLAG_ASSOCIATED**标志，则忽略此标志。 
    
MSGFLAG_RESEND 
  
> 邮件包含与原件报表的重新发送操作的请求。 在客户端或提供程序具有读/写访问此标志直到首次[IMAPIProp::SaveChanges](imapiprop-savechanges.md)调用和只读此后。 
    
MSGFLAG_RN_PENDING 
  
> 阅读的报告需要发送的邮件。 在客户端或提供程序具有到此标志的只读访问权限。 
    
MSGFLAG_SUBMIT 
  
> 邮件标记为发送由于[IMessage::SubmitMessage](imessage-submitmessage.md)调用。 消息存储提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_UNMODIFIED 
  
> 尚未保存; 第一次修改传出消息尚未修改传入邮件，因为它已送达。 
    
MSGFLAG_UNSENT 
  
> 仍正在撰写的邮件。 它保存，但尚未发送。 在客户端或提供程序具有读/写访问此标志直到首次[IMAPIProp::SaveChanges](imapiprop-savechanges.md)调用和只读此后。 如果客户端发送邮件时不设置此标志，消息存储提供程序时调用**IMessage::SubmitMessage**设置它。 通常情况下，此标志为清除状态后发送邮件。 
    
通过调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法读取标志值，客户端或消息存储提供程序可以随时检查邮件的当前状态。 在客户端或提供程序也可以调用[IMAPIProp::SetProps](imapiprop-setprops.md)方法更改当前具有读/写访问任何标志。 
  
有几个标志始终是只读的。 一些读/写，直到为**IMAPIProp::SetProps**而言，第一次调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法和此后将变为只读。 一种，MSGFLAG_READ，可在稍后更改通过[IMessage::SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)。 
  
此属性的初始值通常 MSGFLAG_UNSENT 和 MSGFLAG_UNMODIFIED 以指示一条消息，尚未已发送或更改。 第二次保存后一条消息，消息存储提供程序将清除 MSGFLAG_UNMODIFIED 标志。 消息存储提供程序可以设置一条消息保存时的其他值为 MSGFLAG_HASATTACH 标志，指示邮件包含一个或多个附件。 此设置从计算**PR_HASATTACH**属性。 
  
当客户端调用[IMessage::SubmitMessage](imessage-submitmessage.md)方法来发送消息时，消息存储提供程序创建的 MAPI 后台处理程序的副本，并通过设置 MSGFLAG_SUBMIT 标志更新此属性。 消息存储提供程序还设置 MSGFLAG_UNSENT，如果尚未设置。 MSGFLAG_SUBMIT 指示已调用**SubmitMessage** ，开始发送过程中，并且邮件现在是只读的客户端的。 MSGFLAG_UNSENT 指示 MAPI 后台处理程序处理邮件。 如果取消发送过程，则消息存储提供程序将重置此标志。 
  
时为邮件传递到传输提供程序指定，传输提供程序设置 MSGFLAG_FROMME 标志，如果发件人邮件上已收到消息的服务器上的同一个帐户。 传输提供程序设置为当前登录用户发送的传入消息的 MSGFLAG_FROMME。 客户端可以使用此值以确定它更适合比发件人名称已发送邮件文件夹的内容表中显示收件人姓名。 此外应与收件人姓名，而不是发件人名称显示已在撰写过程中保存和尚未发送的消息。 
  
传入消息，消息存储提供程序清除 MSGFLAG_READ 标志以重置其只读的状态。 客户端可以设置或清除 MSGFLAG_READ 标志时需要更改的只读的状态和控制通过调用消息的[IMessage::SetReadFlag](imessage-setreadflag.md)方法或其文件夹的[IMAPIFolder 发送读取和 nonread 报告：SetReadFlags](imapifolder-setreadflags.md)方法。 这些方法，实现它们的对象之外的主要区别是 folder 方法可以影响一个、 多个，或所有文件夹中的邮件。 消息方法影响一条消息。 
  
客户端还应测试 MSGFLAG_ORIGIN_X400、 MSGFLAG_ORIGIN_INTERNET 和 MSGFLAG_ORIGIN_MISC_EXT flags 的传入消息。 这些标志由入站的传输提供程序设置，指示该消息到达来自网关无法考虑受信任的源。 这意味着发送组织外的邮件或内部但从工作站到网关未知。 在任何情况下，可能未确认的发件人标识，并且没有引入到组织的计算机病毒的风险。 客户端应向用户显示一条警告消息，并提供一个选项，但不打开删除邮件。 
  
消息存储提供程序设置为传入邮件 MSGFLAG_UNMODIFIED 标志。 MSGFLAG_UNMODIFIED 指示传递以来尚未更改一条消息。 消息存储提供程序设置后，客户端无法清除此值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

