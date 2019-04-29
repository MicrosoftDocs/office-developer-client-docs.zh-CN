---
title: 邮件属性概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 447f54de-9f0d-4f73-89b6-bed9cfea9c15
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 515b4637f99b806c5c5bc6304f107f62ca6d9091
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420246"
---
# <a name="message-properties-overview"></a>邮件属性概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 将邮件属性分成三种类型:
  
- 邮件内容属性。
    
- 邮件传输 (即信封) 属性。
    
- 邮件收件人属性。
    
邮件内容属性描述邮件的文本。 每个邮件类都有自己的一组内容属性。 MAPI 为便笺和报告邮件定义内容属性;客户端和消息存储提供程序将负责处理这些类消息, 以适当地为其实现设置属性。 **PR_BODY**([PidTagBody](pidtagbody-canonical-property.md)) 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 是说明邮件的内容属性的示例。 **PR_BODY**包含不带格式的注释内容, 而**PR_RTF_COMPRESSED**包含笔记的格式化内容的压缩版本。 有关属性标识符范围的详细信息, 请参阅[属性标识符范围](property-identifier-ranges.md)。
  
对于新的邮件类别, 客户端可以通过以下两种方式之一定义内容特定属性:
  
- 通过使用自定义邮件类内容属性范围中的属性标识符: 0x6800 到0x7BFF。
    
- 通过使用具有介于0x8000 到0xFFFE 范围的标识符的命名属性。
    
自定义邮件类内容属性的标识符范围适用于任何创建自定义邮件类的客户端。 因此, 此范围中的一个属性标识符可用于多个邮件类别。 此范围中的属性用户不能假定属性行为。 
  
对于命名属性, 客户端创建一个名称, 用于指定属性集以及每个新属性的字符字符串或数值。 然后, 客户端将属性与命名属性范围中的标识符相关联。 通过[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)方法, 命名属性的用户通过名称或标识符访问它们。 
  
信封属性提供用于将邮件从一个收件人传输到另一个收件人的信息。 与邮件内容属性一样, 客户端或服务提供商可以定义自己的信封属性以补充 MAPI 定义的属性。 客户端和传输提供程序根据 mapi 提供的定义设置 mapi 定义的信封属性。 实现特殊功能的传输提供程序可以定义自己的信封属性, 以向客户端公开这些功能。 MAPI 将保留一系列可用于这些特殊提供程序定义属性的属性标识符。 传输提供程序通常会实现一个特殊的属性页, 以显示这些属性, 并使客户端能够更改这些属性。 **PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md)) 和**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 是信封属性的示例。 有关详细信息, 请参阅[属性标识符范围](property-identifier-ranges.md)。
  
收件人属性描述已发送邮件的目标。 收件人可以是邮件用户、通讯组列表或计算机。 收件人属性由 MAPI 定义, 并由服务提供商进行设置。 某些收件人属性受其邮件用户和通讯组列表对象的通讯簿提供程序支持;其他收件人属性由客户端、邮件存储提供程序或传输提供程序支持。 例如, 所有收件人都需要地址和地址类型;这些属性是由通讯簿提供程序在将收件人存储在其某个容器中时维护的属性。 收件人还具有 type, **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)), 它将收件人标识为主副本、抄送收件人或密件抄送收件人。
  
许多邮件属性都是可选的, 这意味着客户端不会期望它们可用或被设置为有效的值。 有些邮件属性是必需的, 但只有在邮件处于特定状态时才可用。 例如, 在保存邮件之前, 新创建的邮件不需要具有条目标识符, 并且在邮件准备好提交之前, 不需要具有邮件类别。 客户端应始终检查其[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)调用的结果, 并将默认值作为备份准备就绪, 以防请求的属性不可用。 
  
服务提供程序设置的大多数邮件属性对客户端而言都是只读的。 
  
## <a name="see-also"></a>另请参阅



[MAPI 邮件](mapi-messages.md)

