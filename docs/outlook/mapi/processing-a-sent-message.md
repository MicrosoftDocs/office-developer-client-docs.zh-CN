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
ms.openlocfilehash: 0cea1a1008ecbff698b757d6c67af5c279954656
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778546"
---
# <a name="processing-a-sent-message"></a>处理已发送的邮件

  
  
**适用于**： Outlook 
  
传出消息后被发送，可以处于发件箱文件夹，移动到文件夹指定用于保存已发送邮件，或删除。 处理的类型取决于已设置属性存储的邮件：
  
- **PR_DELETE_AFTER_SUBMIT**([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 
    
- **PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 
    
 **PR_DELETE_AFTER_SUBMIT**为布尔值属性，否则设置为 TRUE 如果应在后发送，删除消息和 FALSE。 **PR_SENTMAIL_ENTRYID**是文件夹的项标识符。 当设置此属性时，您应将已发送的邮件移动到表示此项标识符的文件夹。 保存的邮件通常具有标识的最后一个消息存储或传输提供程序将发送给他们。 
  
一个或其他，或两个属性都不应设置，但不是能同时。 但是，如果您设置**PR_SENTMAIL_ENTRYID**，它必须包含一个有效项标识符。 
  
下表描述了这些属性如何影响您对于已发送邮件的处理。
  
|||
|:-----|:-----|
|如果既属性设置：  <br/> |将邮件保留从中发送 （通常发件箱） 的文件夹中。  <br/> |
|如果设置**PR_SENTMAIL_ENTRYID** :  <br/> |将邮件移动到指定的文件夹。  <br/> |
|如果设置**PR_DELETE_AFTER_SUBMIT** :  <br/> |删除邮件。  <br/> |
   

