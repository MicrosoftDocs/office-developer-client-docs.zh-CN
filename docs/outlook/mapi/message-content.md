---
title: 邮件内容
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ce643afe-e5b6-42f2-b3cf-4efb957c4f2e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c4d2439c06da292c9cc72c1506a1ae4d10c6704f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435458"
---
# <a name="message-content"></a>邮件内容

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件内容有两种可能的编码: 一种是使用 MIME, 另一种是使用 uuencode。 MIME 是首选的编码。 此外, MAPI 还定义了每个收件人属性**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)), 该属性控制是否应在传出邮件中包含 TNEF 信息。 因此, 对邮件内容进行编码的方法共有四种:
  
- 使用 TNEF 的 MIME
    
- 不采用 TNEF 的 MIME
    
- 使用 TNEF 的 uuencode
    
- 不带 TNEF 的 uuencode
    
如何为未指定出站邮件选择 MIME 或 uuencode。
  
以下属性被排除在 TNEF: **\*PR_SENDER_**、 **PR_ATTACH_DATA_\***、 **PR_BODY**中。 所有其他传输邮件属性都包含在 TNEF 流中。
  
下面的建议旨在提供实现可决定如何支持的参数列表:
  
- 是否对出站邮件使用 MIME 或 uuencode 编码: boolean。
    
- 用于出站邮件的字符集: string (直接复制到字符集参数) 或枚举 (在内部转换为字符集字符串)。
    

