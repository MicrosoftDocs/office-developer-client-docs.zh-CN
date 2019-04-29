---
title: 所有邮件的收件人属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 18c96796-f38d-4058-9c51-9c5a14990846
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3c5764d74039249ccac47d449f0ebd4042893434
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439714"
---
# <a name="recipient-properties-for-all-messages"></a>所有邮件的收件人属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
以下属性通常对所有邮件收件人都存在。 **PR_EMAIL_ADDRESS**和**PR_SEARCH_KEY**是可选的;所有其他属性都是必需的。 
  
**表标题**

|**属性**|**说明**|
|:-----|:-----|
|**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |包含邮件用户的电子邮件地址类型, 例如 SMTP。  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |包含给定 MAPI 对象的显示名称。  <br/> |
|**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |包含一个值, 该值用于将图标与表中的特定行相关联。  <br/> |
|**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))  <br/> |包含邮件用户的电子邮件地址。  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |包含用于打开和编辑特定 MAPI 对象的属性的 MAPI 条目标识符。  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |包含对象的类型。  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |包含二进制可比较的键, 用于标识搜索的相关对象。  <br/> |
   

