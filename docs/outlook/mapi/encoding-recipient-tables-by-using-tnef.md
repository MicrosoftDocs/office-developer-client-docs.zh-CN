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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339401"
---
# <a name="encoding-recipient-tables-by-using-tnef"></a>使用 TNEF 对收件人表进行编码

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
由于大多数邮件系统直接支持收件人列表, 因此很少需要将收件人表的编码转换为 TNEF 流。 通常情况下, 收件人属性在邮件头中传输。 当必须包含收件人表时, TNEF 可以将收件人表编码为其常规处理的一部分。 这是在 TNEF 处理的初始阶段完成的。 传输提供程序可以通过调用包含列表中指定的**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性的[ITnef:: AddProps](itnef-addprops.md)方法来包含邮件的收件人表。 TNEF 从邮件中获取收件人表, 查询列集, 并将表中的每一行处理到 TNEF 流中。
  
如果传输提供程序需要在对收件人表进行编码之前对其进行修改, 则可使用备用方法。 传输提供程序可以构造必要的表, 然后调用[ITnef:: EncodeRecips](itnef-encoderecips.md)方法。 如果在_lpRecipTable_参数中传递 NULL, 则从邮件中直接获取收件人表, 如**ITnef:: AddProps**所述。
  

