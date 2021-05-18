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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5b660b592e77279a4d60f3a036724341352c9b6a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325739"
---
# <a name="pidtagmessageflags-canonical-property"></a>PidTagMessageFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指示邮件的来源和当前状态的标志的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_FLAGS  <br/> |
|标识符:  <br/> |0x0E07  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性是在传输的发送和接收端公开的不可传输邮件属性，根据涉及的客户端应用程序或存储提供程序，其值也不同。 此属性由客户端或邮件存储提供程序在首次创建和保存邮件时初始化，然后由邮件存储提供程序、传输提供程序和 MAPI 后台处理程序在邮件处理和其状态更改时定期更新。 
  
此属性存在于提交之前和之后的邮件上，以及接收的邮件的所有副本上。 虽然该属性不是收件人属性，但根据该收件人已读取或修改它，它向每个收件人公开的方式不同。 
  
可以为此属性设置以下一个或多个标志：
  
MSGFLAG_ASSOCIATED 
  
> 邮件是文件夹的关联邮件。 客户端或提供程序对此标志具有只读访问权限。 对于MSGFLAG_READ邮件，忽略该标记，这些邮件不会保留读/未读状态。 
    
MSGFLAG_FROMME 
  
> 邮件发送用户是接收邮件的邮件用户。 客户端或提供程序对此标志具有读/写访问权限，直到第一次 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 调用和只读之后。 此标志由传输提供程序设置。 
    
MSGFLAG_HASATTACH 
  
> 邮件至少具有一个附件。 此标志对应于[PidTagHasAttachments](pidtaghasattachments-canonical-property.md) PR_HASATTACH (的邮件) 属性。  客户端对此标志具有只读访问权限。 
    
MSGFLAG_NRN_PENDING 
  
> 需要为邮件发送未读报告。 客户端或提供程序对此标志具有只读访问权限。 
    
MSGFLAG_ORIGIN_INTERNET 
  
> 传入的邮件通过 Internet 到达。 它源自组织外部或网关无法认为受信任的源。 客户端应该向用户显示相应的消息。 传输提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_ORIGIN_MISC_EXT 
  
> 传入邮件通过 X.400 或 Internet 外部链接到达。 它源自组织外部或网关无法认为受信任的源。 客户端应该向用户显示相应的消息。 传输提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_ORIGIN_X400 
  
> 传入的邮件通过 X.400 链接到达。 它源自组织外部或网关无法认为受信任的源。 客户端应该向用户显示相应的消息。 传输提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_READ 
  
> 邮件标记为已读。 This can occur as the result of a call at any time to [IMessage：：SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder：：SetReadFlags](imapifolder-setreadflags.md). 客户端还可以在首次保存邮件之前调用邮件的 **IMAPIProp：：SetProps** 方法来设置此标志。 如果设置了此标志 **，MSGFLAG_ASSOCIATED** 此标志。 
    
MSGFLAG_RESEND 
  
> 邮件包含对未送达报告的重新发送操作的请求。 客户端或提供程序对此标志具有读/写访问权限，直到第一次 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 调用和只读之后。 
    
MSGFLAG_RN_PENDING 
  
> 需要为邮件发送阅读报告。 客户端或提供程序对此标志具有只读访问权限。 
    
MSGFLAG_SUBMIT 
  
> 由于调用 [IMessage：：SubmitMessage，邮件被标记为发送](imessage-submitmessage.md)。 邮件存储提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_UNMODIFIED 
  
> 传出邮件自第一次保存以来尚未修改;传入邮件自传递后尚未修改。 
    
MSGFLAG_UNSENT 
  
> 邮件仍在撰写中。 已保存，但尚未发送。 客户端或提供程序对此标志具有读/写访问权限，直到第一次 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 调用和只读之后。 如果客户端在邮件发送时未设置此标志，邮件存储提供程序将在 **调用 IMessage：：SubmitMessage** 时设置它。 通常，此标志在邮件发送后清除。 
    
客户端或邮件存储提供程序可以通过调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来读取标志值，随时检查邮件的当前状态。 客户端或提供程序还可以调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来更改当前具有读/写访问权限的任何标志。 
  
其中几个标志始终为只读。 一些文件是可读写的，直到第一次调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法，之后就 **IMAPIProp：：SetProps** 而言变为只读。 稍后可通过 [IMessage：：SetReadFlag](imessage-setreadflag.md) 或 [IMAPIFolder：：SetReadFlags](imapifolder-setreadflags.md)更改其中一个MSGFLAG_READ，即 "IMessage：：SetReadFlags"。 
  
此属性的初始值通常MSGFLAG_UNSENT MSGFLAG_UNMODIFIED，以指示尚未发送或已更改的邮件。 当邮件第二次保存时，邮件存储提供程序会清除MSGFLAG_UNMODIFIED标记。 邮件存储提供程序在保存邮件时可以设置的另一个值是 MSGFLAG_HASATTACH 标志，指示邮件具有一个或多个附件。 the **PR_HASATTACH** property is computed from this setting. 
  
当客户端调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法发送邮件时，邮件存储提供程序会为 MAPI 后台处理程序创建一个副本，然后通过设置 MSGFLAG_SUBMIT 标志来更新此属性。 如果尚未设置，邮件MSGFLAG_UNSENT提供程序还会设置邮件存储提供程序。 MSGFLAG_SUBMIT表示已调用 **SubmitMessage，** 开始发送过程，并且消息现在对客户端为只读。 MSGFLAG_UNSENT MAPI 后台处理程序正在处理消息。 如果发送过程被取消，邮件存储提供程序将重置此标志。 
  
将邮件给定给传输提供程序进行传递时，如果发件人在邮件传送服务器上具有与接收邮件相同的帐户，则传输提供程序将设置 MSGFLAG_FROMME 标志。 传输提供程序MSGFLAG_FROMME当前登录用户发送的传入邮件的传输提供程序。 客户端可以使用此值来确定在"已发送邮件"文件夹的内容表中显示收件人姓名比显示发件人姓名更合适。 在合成过程中保存但尚未发送的邮件也应使用收件人姓名而不是发件人姓名显示。 
  
对于传入的邮件，邮件存储提供程序会清除 MSGFLAG_READ 标记以重置其读取状态。 客户端可以通过调用邮件的 [IMessage：：SetReadFlag](imessage-setreadflag.md) 方法或文件夹的 [IMAPIFolder：：SetReadFlags](imapifolder-setreadflags.md) 方法，在必要时设置或清除 MSGFLAG_READ 标志，并控制读取和非读取报表的发送。 这些方法之间的主要区别是文件夹方法会影响文件夹中的一个邮件、多个邮件或所有邮件，而不是实现它们的对象。 message 方法影响单个邮件。 
  
客户端还应测试传入邮件的 MSGFLAG_ORIGIN_X400、MSGFLAG_ORIGIN_INTERNET 和 MSGFLAG_ORIGIN_MISC_EXT 标志。 这些标志由入站传输提供程序设置，并指示邮件从网关无法认为受信任的源到达。 这意味着邮件来自组织外部或内部，但来自网关不知道的工作站。 在任何情况下，可能无法确认发件人的身份，并且存在向组织引入计算机病毒的风险。 客户端应该向用户显示一条警告消息，并提供在不打开邮件的情况下删除邮件的选项。 
  
邮件存储提供程序设置MSGFLAG_UNMODIFIED邮件的"邮件"标记。 MSGFLAG_UNMODIFIED邮件表示邮件自传递后未发生更改。 在邮件存储提供程序设置此值后，客户端无法清除此值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

