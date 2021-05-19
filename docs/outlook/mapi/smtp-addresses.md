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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419623"
---
# <a name="smtp-addresses"></a>SMTP 地址

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
SMTP 电子邮件地址的格式在 RFC 822 中定义。 MAPI 组件应处理符合该标准的任何地址。 但是，有一种特定形式的 RFC 822 地址可以最好地对 MAPI 地址进行编码：
  
 _display-name_ **\<**_email-address_**\>**
  
尖括号作为文字包含在内。 空白在显示名称中很常见;它们不需要引用。 典型地址可能如下所示，该地址属于 RFC 1521 的共同作者之一：
  
Nathaniel 一 \< nsb@bellcore.com\>
  
如果显示名称 SMTP 地址（如 或 @）中包含特殊含义的字符，则整个 显示名称 应括在 \< 双引号中。 在出站邮件上，如果电子邮件地址的总长度加上 显示名称超过 255 个字符，显示名称丢弃。
  
SMTP 地址的各个部分映射到 MAPI 属性，如下所示：
  
|**SMTP 地址组件**|**MAPI 属性**|
|:-----|:-----|
| _所有收件人_ 的显示名称  <br/> |**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |
| _From 字段的 display-name_  <br/> |**PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md))   <br/> |
| _发件人字段_ 的显示名称  <br/> |**PR_SENT_REPRESENTING_NAME (** [PidTagSentRepresentingName)](pidtagsentrepresentingname-canonical-property.md)  <br/> |
| _email-address_ <br/> |**PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)  <br/> |
|隐式，始终为"SMTP"  <br/> |**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md))   <br/> |
   
如果入站邮件显示名称地址，应改为使用整个电子邮件地址。 地址类型始终为 SMTP。
  
收件人属性取自 MAPI 邮件的收件人表;发件人属性取自邮件本身。
  

