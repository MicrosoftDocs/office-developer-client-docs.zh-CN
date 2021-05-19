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
  
邮件内容有两种可能的编码：一种使用 MIME，另一种使用 uuencode。 MIME 是首选编码。 此外，MAPI 定义每收件人属性 **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) ，该属性控制是否在传出邮件中包含 TNEF 信息。 因此，总共有四种方法可以编码邮件内容：
  
- MIME 与 TNEF
    
- 没有 TNEF 的 MIME
    
- 使用 TNEF 的 uuencode
    
- 不含 TNEF 的 uuencode
    
未指定如何为出站邮件选择 MIME 或 uuencode。
  
TNEF 中不包括以下属性 **：PR_SENDER_ \*** **\* 、PR_ATTACH_DATA_** **、PR_BODY**。 所有其他可传输邮件属性都包含在 TNEF 流中。
  
以下建议旨在提供实现可决定如何支持的参数列表：
  
- 是使用 MIME 还是 uuencode 对出站邮件进行编码：boolean。
    
- 用于出站邮件的字符集：字符串 (直接复制到 charset 参数) 或枚举 (内部转换为 charset 字符串) 。
    

