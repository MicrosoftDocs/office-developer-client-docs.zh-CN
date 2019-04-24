---
title: 处理已发送的邮件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 55b3e692-753d-45e9-a40d-22adc81b75da
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 880731bf204778cde21da6cd9024a3ca86c6f6a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351063"
---
# <a name="processing-a-sent-message"></a>处理已发送的邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
发送的邮件在发送之后可以保留在 "发件箱" 文件夹中, 移动到指定用于保留已发送邮件的文件夹中, 或被删除。 处理的类型取决于是否设置了邮件存储库属性:
  
- **PR_DELETE_AFTER_SUBMIT**([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 
    
- **PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 
    
 **PR_DELETE_AFTER_SUBMIT**是一个布尔属性, 如果邮件发送后应将其删除, 则设置为 TRUE, 否则设置为 FALSE。 **PR_SENTMAIL_ENTRYID**是文件夹的条目标识符。 设置此属性时, 应将已发送的邮件移动到此条目标识符所表示的文件夹中。 保存的邮件通常具有最后的邮件存储或传输提供程序的标识, 以发送它们。 
  
应设置其中一个或多个属性, 但不能同时设置这两个属性中的任何一个。 但是, 如果设置**PR_SENTMAIL_ENTRYID**, 则它必须包含有效的条目标识符。 
  
下表描述了这些属性如何影响您对已发送邮件所执行的操作。
  
|||
|:-----|:-----|
|如果两个属性都不设置:  <br/> |将邮件保留在发送邮件的文件夹中 (通常为 "发件箱")。  <br/> |
|如果设置了**PR_SENTMAIL_ENTRYID** :  <br/> |将邮件移动到指定的文件夹。  <br/> |
|如果设置了**PR_DELETE_AFTER_SUBMIT** :  <br/> |删除邮件。  <br/> |
   

