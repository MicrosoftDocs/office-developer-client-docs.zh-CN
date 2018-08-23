---
title: SMTP 地址
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 42015740-a94f-4628-bf32-b7fc2fdb9ff6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 655d48d1ea937659f85e0ef7379425759ea7e256
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591357"
---
# <a name="smtp-addresses"></a>SMTP 地址

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
RFC 822 中定义的 SMTP 电子邮件地址的格式。 MAPI 组件应处理任何符合该标准的地址。 但是，没有特定窗体的最佳编码 MAPI 地址的 RFC 822 地址：
  
 _显示名称_**\<** _电子邮件地址_**\>**
  
尖括号都作为包含文字。 空值共有中的显示名称;他们不需要被引用。 典型的地址可能类似于如下，其所属的 RFC 1521 coauthors 之一：
  
Nathaniel Borenstein \<nsb@bellcore.com\>
  
如果显示名称包含字符具有特殊含义 SMTP 地址，如\<或 @，整个的显示名称应括在双引号中。 在出站邮件，如加号的电子邮件地址的总长度显示名称超过 255 个字符，应删除的显示名称。
  
SMTP 地址的部分映射到 MAPI 属性，如下所示：
  
|**SMTP 地址组件**|**MAPI 属性**|
|:-----|:-----|
| 所有收件人的的_显示名称_  <br/> |**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |
| _显示名称_的字段  <br/> |**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |
| 发件人字段的_显示名称_  <br/> |**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))  <br/> |
| _电子邮件地址_ <br/> |**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |
|隐式，始终"SMTP"  <br/> |**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |
   
如果没有显示名称的入站邮件上的地址，应使用的整个电子邮件地址。 地址类型始终是 SMTP。
  
收件人属性均摘自的 MAPI 邮件收件人表;发件人属性来自消息本身。
  

