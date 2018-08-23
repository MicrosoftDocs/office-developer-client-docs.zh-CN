---
title: 邮件属性概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 447f54de-9f0d-4f73-89b6-bed9cfea9c15
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: edbc833b411e56e2efb26631362dd25ea42c3c9f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571407"
---
# <a name="message-properties-overview"></a>邮件属性概述

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 将分为三种类型的邮件属性：
  
- 消息内容的属性。
    
- 邮件传输或信封，属性。
    
- 邮件收件人属性。
    
消息内容属性描述了一条消息的文本。 每个邮件类都有其自己的内容的属性集。 MAPI 定义内容注释和报告消息; 属性由客户端和消息存储提供程序用来处理这些类的消息，以设置其实现适当的属性。 **PR_BODY**([PidTagBody](pidtagbody-canonical-property.md)) 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 是注释消息的内容属性的示例。 **PR_BODY** **PR_RTF_COMPRESSED**包含一条注释的格式化内容的压缩的版本时包含的一条注释，无格式的内容。 有关属性标识符范围的详细信息，请参阅[属性标识符范围](property-identifier-ranges.md)。
  
对于新的邮件类，客户端可以通过两种方式之一定义特定于内容的属性：
  
- 使用自定义消息类内容属性范围内属性标识符： 通过 0x7BFF 0x6800。
    
- 通过使用名为具有属于中通过 0xFFFE 范围 0x8000 的标识符的属性。
    
创建自定义邮件类别的任何客户端可用的自定义消息类内容属性标识符的范围。 因此，在此范围内的一个属性标识符可用于多个邮件类。 此范围中的属性的用户无法进行假设来对行为的属性。 
  
对于命名属性，客户端创建指定属性集和一个字符的字符串或数值的每个新属性的名称。 然后，客户端将属性关联命名的属性区域中的标识符。 用户的命名属性访问它们通过名称或标识符通过[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)方法。 
  
信封属性提供了用于传输到另一条消息从一个收件人的信息。 与邮件内容属性，则可能客户端或服务提供商定义自己的信封属性，来补充那些 MAPI 定义。 客户端和传输提供程序设置信封属性 MAPI 定义基于 MAPI 提供定义。 传输提供程序实现特殊功能可以定义自己的信封属性公开这些客户端功能。 MAPI 留出设置各种属性可用于这些提供程序定义的特殊属性的标识符。 传输提供程序通常实现一个特殊的属性页面来显示这些属性，使客户端可以更改它们。 **PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md)) 和**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 是信封属性的示例。 有关详细信息，请参阅[属性标识符范围](property-identifier-ranges.md)。
  
收件人属性描述发送消息的目标。 收件人可以是邮件用户、 通讯组列表或计算机。 收件人属性通过 MAPI 定义和设置服务提供商。 通讯簿提供程序为其消息的用户和通讯组列表对象; 支持某些收件人属性通过客户端、 消息存储提供程序或传输提供程序支持其他收件人的属性。 例如，所有收件人都需要一个地址和地址类型;这些是当收件人存储及其容器之一时，由通讯簿提供程序维护的属性。 收件人还有类型， **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))，其中将收件人标识为主、 抄送副本或密件抄送副本收件人。
  
许多消息属性是可选的这意味着客户端无法期望它们是可用或设置为有效的值。 某些消息属性是必需的但提供，仅当邮件中的特定状态。 例如，新创建的消息不需要后已保存消息，且不需要具有消息之前准备要提交的邮件类具有直到条目标识符。 客户端应始终检查其[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPIProp::OpenProperty](imapiprop-openproperty.md)调用的结果，并具有默认值作为备份准备好，以防请求的属性不可用。 
  
大多数服务提供商设置的邮件属性是只读的客户端。 
  
## <a name="see-also"></a>另请参阅



[MAPI 邮件](mapi-messages.md)

