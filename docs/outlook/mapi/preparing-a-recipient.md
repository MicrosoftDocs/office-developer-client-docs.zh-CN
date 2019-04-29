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
  
客户端应用程序通过将短期条目标识符转换为长期条目标识符, 并可能添加、更改或重新排序属性来为收件人做准备。 您可以为与邮件无关的邮件或收件人准备收件人列表中的收件人。 通常情况下, 客户端调用[IAddrBook::P reparerecips](iaddrbook-preparerecips.md)直接将短期条目标识符转换为公用地址对话框中包含的收件人的长期条目标识符。 对于与传出邮件关联的收件人, 收件人准备将由名称解析过程处理。 
  
若要准备收件人列表, 请调用**IAddrBook::P reparerecips**。 **PrepareRecips**接受[ADRLIST](adrlist.md)结构和属性标记的列表。 **ADRLIST**结构包含要准备的收件人, 而属性标记列表表示每个收件人应支持的属性。 **PrepareRecips**尝试将属性标记列表中包含的属性放在**ADRLIST**结构的开头。 如果**ADRLIST**结构中缺少列表中的任何属性, 则 MAPI 会调用通讯簿提供程序来提供它们。 如果只需要检查长期条目标识符, 请为_lpSPropTagArray_参数传递 NULL。 
  
例如, 假设您正在处理五个收件人。 所有五个收件人都按以下顺序显示在**ADRLIST**结构中, 其属性如下: 
  
1. **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))
    
2. **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))
    
3. **PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))
    
4. **PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))
    
5. **PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))
    
前两个收件人的**ADRLIST**结构中包含了其他三个属性。 
  
1. **PR_ACCOUNT**([PidTagAccount](pidtagaccount-canonical-property.md))
    
2. **PR_GIVEN_NAME**([PidTagGivenName](pidtaggivenname-canonical-property.md))
    
3. **PR_SURNAME**([PidTagSurname](pidtagsurname-canonical-property.md))
    
由于所有收件人都需要将其作为前三个属性**PR_ADDRTYPE**、 **PR_ENTRYID**和**PR_HOME_TELEPHONE_NUMBER** ([PidTagHomeTelephoneNumber](pidtaghometelephonenumber-canonical-property.md)), 请使用这些属性创建一个 property 标记数组并传递将其和**ADRLIST**结构的**PrepareRecips**。 **PrepareRecips**调用每个收件人的**IMAPIProp:: GetProps**方法以检索**PR_HOME_TELEPHONE_NUMBER** , 因为它当前不是**ADRLIST**结构的一部分。 当**PrepareRecips**返回时, 收件人列表表示收件人的合并列表, 其中包含在**ADRLIST**结构中包含在每个收件人的第一个显示的属性。 
  
收件人1和组2的收件人列表包含按以下顺序排列的属性:
  
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
    
收件人3、4和5的收件人列表包括按以下顺序列出的属性:
  
1. **PR_ADDRTYPE**
    
2. **PR_ENTRYID**
    
3. **PR_HOME_TELEPHONE_NUMBER**
    
4. **PR_DISPLAY_NAME**
    
5. **PR_SEARCH_KEY**
    
6. **PR_EMAIL_ADDRESS**
    
7. **PR_ADDRTYPE**
    
作为调用 IAddrBook 的替代方法 **::P reparerecips**若要使用属性, 请调用每个收件人的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法, 并在必要时调用其[IMAPIProp:: SetProps](imapiprop-setprops.md)方法。 当只涉及一个收件人时, 一种方法就是令人满意。 但是, 当涉及多个收件人时, 调用**PrepareRecips**而不是**IMAPIProp**方法可节省时间, 并且, 如果您正在远程操作, 很多远程过程调用。 **PrepareRecips**处理单个呼叫中的所有收件人, 而**GetProps**和**SetProps**为每个收件人发出一个呼叫。 
  

