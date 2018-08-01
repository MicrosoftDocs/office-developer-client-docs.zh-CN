---
title: 创建收件人列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 270f86dd-2c1f-47eb-80f7-9d0d63936d61
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fa23377a8b080ae9dac3e31dfa137ca03a242c74
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774747"
---
# <a name="creating-a-recipient-list"></a>创建收件人列表

  
  
**适用于**： Outlook 
  
收件人列表是每个邮件收件人中包含的属性值结构数组[ADRLIST](adrlist.md)结构 — 目标的邮件。 收件人可以表示 human 用户、 计算机或文件夹。 要发送的所有邮件都需要至少一个收件人的已通过名称解析过程的 — 确保**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的收件人的属性值数组中包含的过程。 
  
收件人的属性为通讯簿属性和邮件属性的组合。 收件人属性可应用于所有邮件的特定收件人或仅对当前邮件。 同时消息存储和传输提供程序可以设置收件人属性。 
  
已准备好发送邮件时，每个收件人必须其属性值阵列中有一组核心属性。 组所需的收件人属性包括：
  
- **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
- **PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 
    
- **PR_ENTRYID**
    
- **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 
    
- **PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 
    
访问收件人、 向其发送消息和要与其他人使用这些属性。 并非所有这些属性所要立即可用。 您可以添加收件人最初不知道其条目标识符，依赖于名称解析过程分配此属性。 某个时刻发送一条消息之前，请调用[IAddrBook::ResolveName](iaddrbook-resolvename.md)以确保所有收件人列表中的收件人解析。 有关详细信息，请参阅[解析收件人姓名](resolving-a-recipient-name.md)。
  
从消息用户或通讯簿容器中的通讯组列表项或 one-offs，可以创建收件人列表。 One-offs 是作为临时条目只能用于解决单个邮件或条目添加到个人通讯簿创建的收件人。 一次性条目标识符和地址的格式由 MAPI 定义。 有关这些格式的详细信息，请参阅[一次性地址](one-off-addresses.md)和[一次性条目标识符](one-off-entry-identifiers.md)。
  
您可以让用户能够构建其收件人列表：
  
- 仅与通讯簿中的条目。
    
- 仅与一次性条目。
    
- 与通讯簿收件人和 one-offs 的组合。
    
 **创建使用通用的地址对话框的收件人列表**
  
1. 分配[ADRPARM](adrparm.md)结构和指向[ADRLIST](adrlist.md)结构的指针。 
    
2. 零**ADRPARM**结构中的内存和**ADRLIST**指针设置为 NULL。 
    
3. 调用[IAddrBook::Address](iaddrbook-address.md)显示地址对话框并填充**ADRPARM**结构。 
    
4. 调用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)，传递**ADRLIST**指针。 此结构将包含每个用户所选定的收件人的属性。 
    
 **以编程方式创建收件人列表**
  
1. 分配**ADRLIST**结构，其中包含每个收件人包含在列表中的一个[ADRENTRY](adrentry.md)结构。 使每个**ADRENTRY**结构足以容纳每个必需的属性和**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))。
    
2. 对于每个收件人，设置**ADRLIST**结构及其**aEntries**成员属性值数组。 
    
3. 调用设置了 MODRECIP_ADD 标志[IMessage::ModifyRecipients](imessage-modifyrecipients.md) 。 
    

