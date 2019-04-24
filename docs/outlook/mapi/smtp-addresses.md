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
ms.openlocfilehash: fb4402100891df8b27c8d26900a4acd05f4183e3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344560"
---
# <a name="smtp-addresses"></a>SMTP 地址

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
SMTP 电子邮件地址的格式是在 RFC 822 中定义的。 MAPI 组件应处理符合该标准的任何地址。 但是, 有一种特定形式的 RFC 822 地址, 可以最大限度地编码 MAPI 地址:
  
 _显示-名称_**\<** _电子邮件地址_**\>**
  
尖括号以文本形式包含。 空白在显示名称中是通用的;不需要报价。 典型的地址可能如下所示, 属于 RFC 1521 的合著者之一:
  
Nathaniel Borenstein \<nsb@bellcore.com\>
  
如果显示名称包含在 SMTP 地址中有特殊含义的字符 (如\<或 @), 则应使用双引号将整个显示名称括起来。 在出站邮件中, 如果电子邮件地址的总长度加上显示名称超过255个字符, 则应删除显示名称。
  
SMTP 地址的各个部分映射到 MAPI 属性, 如下所示:
  
|**SMTP 地址组件**|**MAPI 属性**|
|:-----|:-----|
| _显示-_ 所有收件人的姓名  <br/> |**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |
| "_显示-_ 源中的名称" 字段  <br/> |**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |
| "_显示-_ 发件人的名称" 字段  <br/> |**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))  <br/> |
| _电子邮件地址_ <br/> |**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |
|隐式, 始终为 "SMTP"  <br/> |**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |
   
如果入站邮件上的地址没有显示名称, 则应改为使用整个电子邮件地址。 地址类型始终为 SMTP。
  
收件人属性是从 MAPI 邮件的收件人表中获取的;发件人属性是从邮件本身获取的。
  

