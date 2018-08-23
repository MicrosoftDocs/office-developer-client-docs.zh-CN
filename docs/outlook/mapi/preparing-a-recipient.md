---
title: 准备收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9573f10c-66e1-4e87-93f0-89687e906b8b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b4ccfb8cf8201a17993932acc4c0104ace80b94d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588718"
---
# <a name="preparing-a-recipient"></a>准备收件人

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
客户端应用程序通过将其短期条目标识符格式转换为长期条目标识符和可能添加、 更改或重新排序属性准备收件人。 您可以准备属于邮件的收件人列表的收件人或一条消息，与无关的收件人。 通常情况下，客户端调用[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)直接要转换为长期条目标识符的短期条目标识符的通用的地址对话框中包含的收件人。 对于与传出邮件的收件人，收件人准备进行处理的名称解析过程。 
  
若要准备的收件人列表，请调用**IAddrBook::PrepareRecips**。 **PrepareRecips**接受[ADRLIST](adrlist.md)结构和属性标记的列表。 **ADRLIST**结构包含属性标记列表代表应支持每个收件人的属性时要准备的收件人。 **PrepareRecips**尝试将放置**ADRLIST**结构开头属性标记列表中包含的属性。 如果有**ADRLIST**结构中缺少的属性列表中，MAPI 调用通讯簿提供程序提供它们。 如果您只需检查长期条目标识符， _lpSPropTagArray_参数传递 NULL。 
  
例如，假设您正在使用 5 个收件人。 所有五个收件人**ADRLIST**结构中出现与以下顺序中的以下属性： 
  
1. **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
2. **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
3. **PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))
    
4. **PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))
    
5. **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
**ADRLIST**结构中的前两个收件人包含三个其他属性。 
  
1. **PR_ACCOUNT**([PidTagAccount](pidtagaccount-canonical-property.md))
    
2. **PR_GIVEN_NAME**([PidTagGivenName](pidtaggivenname-canonical-property.md))
    
3. **PR_SURNAME**([PidTagSurname](pidtagsurname-canonical-property.md))
    
由于的所有收件人都需要具有**PR_ADDRTYPE**、 **PR_ENTRYID**和**PR_HOME_TELEPHONE_NUMBER** ([PidTagHomeTelephoneNumber](pidtaghometelephonenumber-canonical-property.md)) 及其前三个属性，这些属性与创建属性标记数组和传递它并**PrepareRecips** **ADRLIST**结构。 **PrepareRecips**调用每个收件人的**IMAPIProp::GetProps**方法来检索**PR_HOME_TELEPHONE_NUMBER** ，因为它不当前**ADRLIST**结构的一部分。 **PrepareRecips**返回时，收件人列表中的每个收件人显示第一个**ADRLIST**结构包括的属性表示合并的收件人列表。 
  
1 和 2 的收件人的收件人列表包括按以下顺序的属性：
  
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
    
收件人 3、 4 和 5 的收件人列表包括按以下顺序的属性：
  
1. **PR_ADDRTYPE**
    
2. **PR_ENTRYID**
    
3. **PR_HOME_TELEPHONE_NUMBER**
    
4. **PR_DISPLAY_NAME**
    
5. **PR_SEARCH_KEY**
    
6. **PR_EMAIL_ADDRESS**
    
7. **PR_ADDRTYPE**
    
作为调用**IAddrBook::PrepareRecips**用于属性的替代方法，调用每个收件人的[IMAPIProp::GetProps](imapiprop-getprops.md)方法，如有必要，其[IMAPIProp::SetProps](imapiprop-setprops.md)方法。 涉及仅有一个收件人时，令人满意上述任一方法。 但是，涉及多个收件人时，调用**PrepareRecips** ，而不是**IMAPIProp**方法节省时间，如果您在远程运行多个远程过程调用。 **PrepareRecips**处理一次调用中的所有收件人，而**GetProps**和**SetProps**进行一次调用每个收件人。 
  

