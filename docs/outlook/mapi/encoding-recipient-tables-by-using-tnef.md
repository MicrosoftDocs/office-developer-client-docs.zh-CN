---
title: 使用 TNEF 对收件人表进行编码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cd2f595f-4dd0-4704-b670-6857d6c843ca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1ed047424e4a6d64c08b511a15769c081a0d8c4e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417957"
---
# <a name="encoding-recipient-tables-by-using-tnef"></a>使用 TNEF 对收件人表进行编码

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
很少需要将收件人表编码到 TNEF 流中，因为大多数邮件系统直接支持收件人列表。 通常，收件人属性在邮件头中传输。 如果需要包含收件人表，TNEF 可以将收件人表编码为通常处理的一部分。 这是在 TNEF 处理的初始阶段完成。 传输提供程序可以使用包含列表中指定的 **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性调用 [ITnef：：AddProps](itnef-addprops.md)方法，以包含邮件的收件人表。 TNEF 从邮件获取收件人表，查询列集，将表的每一行处理到 TNEF 流中。
  
如果传输提供程序需要先修改收件人表，然后再对其进行编码，则可用备用方法。 传输提供程序可以构造必要的表，然后调用 [ITnef：：EncodeRecips](itnef-encoderecips.md) 方法。 如果在  _lpRecipTable_ 参数中传递 NULL，则直接从邮件中接收收件人表，如 **ITnef：：AddProps 中所述**。
  

