---
title: 创建收件人列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 270f86dd-2c1f-47eb-80f7-9d0d63936d61
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e3aa1f2b2e1e7c6d8a9be3fff451002952930ffb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428212"
---
# <a name="creating-a-recipient-list"></a>创建收件人列表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
收件人列表是一个 [ADRLIST](adrlist.md) 结构，包含每个邮件收件人的属性值结构数组 — 邮件的目标。 收件人可以代表用户、计算机或文件夹。 要发送的所有邮件都至少需要一个已执行名称解析过程的收件人， 这是确保 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性包含在收件人的属性值数组中的过程。 
  
收件人的属性是通讯簿属性和邮件属性的组合。 收件人属性可以应用于特定收件人的所有邮件，也可以只应用于当前邮件。 邮件存储和传输提供程序都可以设置收件人属性。 
  
在准备好发送邮件时，每个收件人的属性值数组中都必须有一组核心属性。 所需的收件人属性集包括：
  
- **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md))  
    
- **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))  
    
- **PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md) 
    
- **PR_ENTRYID**
    
- **PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))  
    
- **PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md))  
    
这些属性用于访问收件人、向收件人发送邮件以及将其与其他收件人进行比较。 并非所有这些属性都需要马上可用。 您可以最初添加收件人，而无需知道其条目标识符，而依赖名称解析过程来分配此属性。 在发送邮件之前，请调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 以确保收件人列表中的所有收件人已解析。 有关详细信息，请参阅 [解析收件人姓名](resolving-a-recipient-name.md)。
  
收件人列表可以从通讯簿容器中的邮件用户或通讯组列表条目创建，也可以从一次发送创建。 一对多是作为临时条目创建的收件人，仅用于处理单个邮件，或创建为要添加到个人通讯簿中的条目。 一次输入标识符和地址的格式由 MAPI 定义。 有关这些格式的信息，请参阅 [一次使用](one-off-addresses.md) 地址和 [一次使用条目标识符](one-off-entry-identifiers.md)。
  
您可以允许用户构建其收件人列表：
  
- 仅包含通讯簿中的条目。
    
- 仅包含一次输入。
    
- 结合使用通讯簿收件人和一键式。
    
 **使用公用地址对话框创建收件人列表**
  
1. 分配 [ADRPARM](adrparm.md) 结构和指向 [ADRLIST](adrlist.md) 结构的指针。 
    
2. 将 **ADRPARM** 结构中的内存清零，将 **ADRLIST** 指针设置为 NULL。 
    
3. 调用 [IAddrBook：：Address](iaddrbook-address.md) 以显示地址对话框并填充 **ADRPARM** 结构。 
    
4. 调用 [IMessage：：ModifyRecipients，](imessage-modifyrecipients.md)传递 **ADRLIST** 指针。 此结构将包含用户选择的每个收件人的属性。 
    
 **以编程方式创建收件人列表**
  
1. 为要包含在列表中的每个收件人分配包含一个 [ADRENTRY](adrentry.md)结构的 **ADRLIST** 结构。 使每个 **ADRENTRY** 结构足够大，以容纳每个必需的属性PR_RECIPIENT_TYPE ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 。 
    
2. 对于每个收件人，在 **ADRLIST** 结构中设置 **其 aEntries** 成员属性值数组。 
    
3. 调用 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 并设置MODRECIP_ADD标志。 
    

