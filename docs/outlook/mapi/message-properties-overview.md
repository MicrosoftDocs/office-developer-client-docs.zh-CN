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
  
MAPI 将邮件属性分为三种类型：
  
- 邮件内容属性。
    
- 邮件传输或信封属性。
    
- 邮件收件人属性。
    
邮件内容属性描述邮件的文本。 每个邮件类都有自己的一组内容属性。 MAPI 定义便笺和报表邮件的内容属性;由处理这些邮件类的客户端和邮件存储提供程序来设置适合其实现的属性。 **PR_BODY (** [PidTagBody](pidtagbody-canonical-property.md)) PR_RTF_COMPRESSED ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 是笔记消息的内容属性示例。  **PR_BODY** 包含注释的无格式内容，PR_RTF_COMPRESSED包含注释格式化内容的压缩版本。  有关属性标识符范围的信息，请参阅属性 [标识符范围](property-identifier-ranges.md)。
  
对于新邮件类，客户端可以通过两种方式之一定义特定于内容的属性：
  
- 通过使用自定义邮件类内容属性范围中的属性标识符：0x6800到0x7BFF。
    
- 通过使用具有标识符的已命名属性，这些标识符0x8000范围0xFFFE范围。
    
自定义邮件类内容属性的标识符范围可用于创建自定义邮件类的任何客户端。 因此，此范围中的一个属性标识符可用于多个邮件类。 此范围内属性的用户无法对属性的行为做出假设。 
  
对于命名属性，客户端会创建一个名称，用于指定属性集以及每个新属性的字符串或数值。 然后，客户端将该属性与命名属性范围中的标识符关联。 命名属性的用户通过 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 和 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 方法按名称或标识符访问它们。 
  
信封属性提供用于将邮件从一个收件人传输到另一个收件人的信息。 与邮件内容属性一样，客户端或服务提供商可以定义自己的信封属性来补充 MAPI 定义的信封属性。 客户端和传输提供程序根据 MAPI 提供的定义设置 MAPI 定义的信封属性。 实现特殊功能的传输提供程序可以定义自己的信封属性，以向客户端公开这些功能。 MAPI 留出了一系列可用于这些特殊提供程序定义属性的属性标识符。 传输提供程序通常实现一个特殊的属性页来显示这些属性，并允许客户端更改它们。 **PR_SUBJECT (** [PidTagSubject](pidtagsubject-canonical-property.md)) 和 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 是信封属性的示例。 有关详细信息，请参阅属性 [标识符范围](property-identifier-ranges.md)。
  
收件人属性描述已发送邮件的目标。 收件人可以是邮件用户、通讯组列表或计算机。 收件人属性由 MAPI 定义，由服务提供商设置。 某些收件人属性受通讯簿提供程序支持，用于邮件用户和通讯组列表对象;客户端、邮件存储提供程序或传输提供程序支持其他收件人属性。 例如，所有收件人都需要地址和地址类型;这些是通讯簿提供程序维护的属性，当收件人存储在其容器之一中时。 收件人还有一个类型 **，PR_RECIPIENT_TYPE (** [PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) ，该类型将收件人标识为主要、抄件或密件抄件收件人。
  
许多邮件属性是可选的，这意味着客户端无法期望它们可用或设置为有效值。 某些邮件属性是必需的，但仅在邮件位于特定状态时可用。 例如，在保存邮件之前，新创建的邮件不需要具有条目标识符，在准备好提交邮件之前，不需要具有邮件类。 客户端应始终检查 [其 IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 调用的结果，并准备好默认值作为备份，以防请求的属性不可用。 
  
服务提供商设置大多数邮件属性对于客户端都是只读的。 
  
## <a name="see-also"></a>另请参阅



[MAPI 邮件](mapi-messages.md)

