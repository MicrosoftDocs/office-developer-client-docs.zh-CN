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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434674"
---
# <a name="processing-a-sent-message"></a>处理已发送的邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
传出邮件发送后，可以将其留在"发件箱"文件夹中，移动到指定用于保留已发送邮件的文件夹，也可以将其删除。 处理类型取决于是否已设置邮件存储属性：
  
- **PR_DELETE_AFTER_SUBMIT (** [PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))  
    
- **PR_SENTMAIL_ENTRYID (** [PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))  
    
 **PR_DELETE_AFTER_SUBMIT** Boolean 属性，如果邮件应在发送后删除，则设置为 TRUE;否则设置为 FALSE。 **PR_SENTMAIL_ENTRYID** 是文件夹的条目标识符。 设置此属性后，应该将已发送的邮件移动到此条目标识符表示的文件夹。 保存的邮件通常具有要发送的最后一封邮件存储或传输提供程序的标识。 
  
应设置其中一个或另一个，或这两个属性都不设置，但不能同时设置两者。 但是， **如果您将** PR_SENTMAIL_ENTRYID ，则它必须包含有效的条目标识符。 
  
下表介绍了这些属性如何影响您处理已发送邮件时所执行操作。
  
|||
|:-----|:-----|
|如果两个属性都未设置：  <br/> |将邮件留在从其中发送邮件的文件夹中 (通常是发件箱) 。  <br/> |
|如果 **PR_SENTMAIL_ENTRYID** 设置：  <br/> |将邮件移动到指示的文件夹。  <br/> |
|如果 **PR_DELETE_AFTER_SUBMIT** 设置：  <br/> |删除邮件。  <br/> |
   

