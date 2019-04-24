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
  
包含指示邮件的源和当前状态的标志的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_FLAGS  <br/> |
|标识符:  <br/> |0x0E07  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性是在传输的发送端和接收端公开的 nontransmittable 消息属性, 具有不同的值, 具体取决于所涉及的客户端应用程序或存储提供程序。 此属性由客户端或邮件存储提供程序在邮件首次创建和保存时进行初始化, 并在邮件存储提供程序、传输提供程序和 MAPI 后台处理程序定期更新, 同时处理邮件及其状态更新. 
  
此属性在提交之前和之后都存在于邮件中, 并在收到的邮件的所有副本上。 尽管它不是收件人属性, 但根据收件人是否已被该收件人阅读或修改, 它会以不同方式公开给每个收件人。 
  
可以为此属性设置以下一个或多个标志:
  
MSGFLAG_ASSOCIATED 
  
> 邮件是文件夹的关联邮件。 客户端或提供程序具有此标志的只读访问权限。 对于不保留已读/未读状态的关联邮件, 将忽略 MSGFLAG_READ 标志。 
    
MSGFLAG_FROMME 
  
> 邮件传递用户发送是接收邮件的邮件用户。 客户端或提供程序对此标志具有读/写访问权限, 直到第一个[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用和此后为只读。 此标志应由传输提供程序进行设置。 
    
MSGFLAG_HASATTACH 
  
> 邮件至少有一个附件。 此标志对应于邮件的**PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md)) 属性。 客户端对此标志具有只读访问权限。 
    
MSGFLAG_NRN_PENDING 
  
> 需要为邮件发送未读报告。 客户端或提供程序具有此标志的只读访问权限。 
    
MSGFLAG_ORIGIN_INTERNET 
  
> 通过 Internet 到达的传入邮件。 它来源于组织外部或网关无法视为受信任的源。 客户端应向用户显示适当的消息。 传输提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_ORIGIN_MISC_EXT 
  
> 传入邮件通过除 X. 400 或 Internet 之外的外部链接到达。 它来源于组织外部或网关无法视为受信任的源。 客户端应向用户显示适当的消息。 传输提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_ORIGIN_X400 
  
> 传入邮件通过 400. 400 链接到达。 它来源于组织外部或网关无法视为受信任的源。 客户端应向用户显示适当的消息。 传输提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_READ 
  
> 邮件被标记为已读。 在任何时候调用[IMessage:: SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)时, 都会发生这种情况。 在首次保存邮件之前, 客户端还可以通过调用邮件的**IMAPIProp:: SetProps**方法来设置此标志。 如果设置了**MSGFLAG_ASSOCIATED**标志, 则忽略此标志。 
    
MSGFLAG_RESEND 
  
> 该邮件包含一个使用 nondelivery 报告的重发操作请求。 客户端或提供程序对此标志具有读/写访问权限, 直到第一个[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用和此后为只读。 
    
MSGFLAG_RN_PENDING 
  
> 需要为邮件发送已读报告。 客户端或提供程序具有此标志的只读访问权限。 
    
MSGFLAG_SUBMIT 
  
> 由于调用[IMessage:: SubmitMessage](imessage-submitmessage.md), 邮件被标记为要发送。 邮件存储提供程序设置此标志;客户端具有只读访问权限。 
    
MSGFLAG_UNMODIFIED 
  
> 传出邮件自第一次保存后未进行过修改;传入邮件自传递后未进行修改。 
    
MSGFLAG_UNSENT 
  
> 邮件仍在撰写中。 它将被保存, 但尚未发送。 客户端或提供程序对此标志具有读/写访问权限, 直到第一个[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用和此后为只读。 如果客户端在发送邮件时不设置此标记, 则邮件存储提供程序会在调用**IMessage:: SubmitMessage**时对其进行设置。 通常情况下, 在发送邮件后清除此标志。 
    
通过调用[IMAPIProp:: GetProps](imapiprop-getprops.md)方法读取标志值, 客户端或邮件存储提供程序可以随时检查邮件的当前状态。 客户端或提供程序也可以调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法来更改当前具有读/写访问权限的任何标志。 
  
有些标志始终为只读。 有些是可读写的, 直到第一次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法, 之后, 在**IMAPIProp:: SetProps**相关时将变为只读。 可以在稍后通过[IMessage:: SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)更改其中一个 MSGFLAG_READ。 
  
此属性的初始值通常为 MSGFLAG_UNSENT 和 MSGFLAG_UNMODIFIED, 以指示尚未发送或更改的邮件。 在第二次保存邮件时, 邮件存储提供程序将清除 MSGFLAG_UNMODIFIED 标志。 保存邮件时, 邮件存储提供程序可以设置的另一个值是 MSGFLAG_HASATTACH 标志, 指示邮件包含一个或多个附件。 **PR_HASATTACH**属性是从此设置计算而来。 
  
当客户端调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法发送邮件时, 邮件存储提供程序会为 MAPI 后台处理程序创建一个副本, 并通过设置 MSGFLAG_SUBMIT 标志来更新该属性。 如果尚未设置, 邮件存储提供程序还会设置 MSGFLAG_UNSENT。 MSGFLAG_SUBMIT 指示已调用**SubmitMessage** , 即将开始发送过程, 并且该邮件目前对客户端是只读的。 MSGFLAG_UNSENT 指示 MAPI 后台处理程序正在处理该邮件。 如果发送过程被取消, 邮件存储提供程序将重置此标志。 
  
将邮件传递给传输提供程序进行传递时, 如果发件人在邮件服务器上具有相同的帐户, 则传输提供程序将设置 MSGFLAG_FROMME 标志 (如果在上接收邮件)。 传输提供程序为当前登录用户发送的传入邮件设置 MSGFLAG_FROMME。 客户端可以使用此值来确定更适合在 "已发送邮件" 文件夹的 "内容" 表中显示收件人姓名。 在撰写过程中保存但尚未发送的邮件也应显示收件人姓名而不是发件人姓名。 
  
对于传入邮件, 邮件存储提供程序将清除 MSGFLAG_READ 标志以重置其读取状态。 当需要更改读取状态并控制读取和未读报告的发送时, 客户端可以设置或清除 MSGFLAG_READ 标志, 方法是调用邮件的[IMessage:: SetReadFlag](imessage-setreadflag.md)方法或其文件夹的[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)方法。 这些方法 (而不是实现它们的对象) 之间的主要区别是, folder 方法可以影响文件夹中的一个、多个或所有邮件。 message 方法影响单个邮件。 
  
客户端还应为 MSGFLAG_ORIGIN_X400、MSGFLAG_ORIGIN_INTERNET 和 MSGFLAG_ORIGIN_MISC_EXT 标志测试传入的邮件。 这些标志由入站传输提供程序设置, 并指示邮件到达来自网关无法认为受信任的源。 这意味着邮件在组织外部, 或在内部, 而不是由网关所知的工作站发起。 在任何情况下, 可能不会确认发件人的身份, 并且存在将计算机病毒引入组织的风险。 客户端应向用户显示一条警告消息, 并提供在不打开邮件的情况下删除邮件的选项。 
  
邮件存储提供程序设置传入邮件的 MSGFLAG_UNMODIFIED 标志。 MSGFLAG_UNMODIFIED 指示邮件自传递后未发生更改。 客户端无法在邮件存储提供程序设置后清除此值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

