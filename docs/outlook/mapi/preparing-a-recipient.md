---
title: 准备收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9573f10c-66e1-4e87-93f0-89687e906b8b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bb6bc8b8d0199ab07d5dad353dbc25da240593e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419875"
---
# <a name="preparing-a-recipient"></a>准备收件人

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序通过将收件人的短期条目标识符转换为长期条目标识符，并可能添加、更改或重新排序属性来准备收件人。 您可以为邮件准备属于收件人列表的收件人，也可以准备与邮件无关的收件人。 通常，客户端直接调用 [IAddrBook：:P repareRecips，](iaddrbook-preparerecips.md) 将短期条目标识符转换为包含在公用地址对话框中的收件人的长期条目标识符。 对于与传出邮件相关联的收件人，收件人准备由名称解析过程处理。 
  
若要准备收件人列表，请调用 **IAddrBook：:P repareRecips**。 **PrepareRecips** 接受 [ADRLIST](adrlist.md) 结构和属性标记列表。 **ADRLIST** 结构包含要准备的收件人，而属性标记列表表示每个收件人应支持的属性。 **PrepareRecips** 尝试将属性标记列表中包含的属性放在 **ADRLIST** 结构的开头。 如果 **ADRLIST** 结构中缺少列表中的任何属性，MAPI 将调用通讯簿提供程序提供这些属性。 如果只需要检查长期条目标识符，请为  _lpSPropTagArray_ 参数传递 NULL。 
  
例如，假设您正在处理五个收件人。 所有五个收件人都按以下顺序显示在 **ADRLIST** 结构中，并具有以下属性： 
  
1. **PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 
    
2. **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 
    
3. **PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 
    
4. **PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)
    
5. **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 
    
前两个收件人的 **ADRLIST** 结构中包含其他三个属性。 
  
1. **PR_ACCOUNT (** [PidTagAccount)](pidtagaccount-canonical-property.md)
    
2. **PR_GIVEN_NAME (** [PidTagGivenName](pidtaggivenname-canonical-property.md)) 
    
3. **PR_SURNAME (** [PidTagSurname](pidtagsurname-canonical-property.md)) 
    
由于所有收件人都需要将 **PR_ADDRTYPE、PR_ENTRYID** 和 **PR_HOME_TELEPHONE_NUMBER** ([PidTagHomeTelephoneNumber](pidtaghometelephonenumber-canonical-property.md)) 属性作为前三个属性，因此使用这些属性创建一个属性标记数组，并传递此属性和 **ADRLIST** 结构到 **PrepareRecips**。  **PrepareRecips** 调用每个收件人的 **IMAPIProp：：GetProps** 方法来检索 **PR_HOME_TELEPHONE_NUMBER因为它当前** 不是 **ADRLIST** 结构的一部分。 当 **PrepareRecips** 返回时，收件人列表表示收件人的合并列表，其中每个收件人首先显示 **ADRLIST** 结构中包含的属性。 
  
收件人 1 和收件人 2 的收件人列表包括按以下顺序的属性：
  
1. **PR_ADDRTYPE**
    
2. **PR_ENTRYID**
    
3. **PR_HOME_TELEPHONE_NUMBER**
    
4. **PR_DISPLAY_NAME**
    
5. **PR_SEARCH_KEY**
    
6. **PR_EMAIL_ADDRESS**
    
7. **PR_ADDRTYPE**
    
8. **PR_ACCOUNT**
    
9. **PR_GIVEN_NAME**
    
10. **PR_SURNAME**
    
收件人 3、4 和 5 的收件人列表按以下顺序包括属性：
  
1. **PR_ADDRTYPE**
    
2. **PR_ENTRYID**
    
3. **PR_HOME_TELEPHONE_NUMBER**
    
4. **PR_DISPLAY_NAME**
    
5. **PR_SEARCH_KEY**
    
6. **PR_EMAIL_ADDRESS**
    
7. **PR_ADDRTYPE**
    
作为调用 **IAddrBook：:P repareRecips** 以使用属性的替代方法，请调用每个收件人的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法，并在必要时调用其 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。 如果只涉及一个收件人，则任一技术都满意。 但是，当涉及多个收件人时，调用 **PrepareRecips（** 而不是 **IMAPIProp** 方法）可以节省时间，并且，如果远程操作，则调用许多远程过程。 **PrepareRecips** 在单个呼叫中处理所有收件人， **而 GetProps** 和 **SetProps** 则针对每个收件人进行一次呼叫。 
  

