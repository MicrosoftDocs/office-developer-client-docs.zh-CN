---
title: 邮件内容
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ce643afe-e5b6-42f2-b3cf-4efb957c4f2e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 85bd3f7db53f195295405fb0b02c25f084786a67
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586079"
---
# <a name="message-content"></a>邮件内容

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
有两个可能的消息内容编码： 一个使用 MIME，其他使用 uuencode。 MIME 是首选编码。 此外，MAPI 定义的每个收件人属性， **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md))，其控制 TNEF 信息应包含传出邮件中。 因此，共有四种方式的编码消息内容的：
  
- 使用 TNEF MIME
    
- MIME TNEF 的情况下
    
- 使用 TNEF 的 uuencode
    
- uuencode 不 TNEF
    
未指定如何选择 MIME 或 uuencode 出站邮件。
  
从 TNEF 排除以下属性： **PR_SENDER_\***， **PR_ATTACH_DATA_\***， **PR_BODY**。 TNEF 用于将 stream 中包含其他可传输的消息中的所有属性。
  
以下建议旨在提供实现可以决定如何支持的参数的列表：
  
- 是否要编码的出站邮件使用 MIME 或 uuencode: boolean。
    
- 字符集用于出站邮件: （直接复制到 charset 参数） 的字符串或枚举 （转换内部为 charset 字符串）。
    

