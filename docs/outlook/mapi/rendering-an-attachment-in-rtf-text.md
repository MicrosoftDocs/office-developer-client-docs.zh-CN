---
title: 以 RTF 文本呈现附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 26372539-e9fe-464d-95c7-90b58c20b98f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5d8fc10f876408d616c5acefb664ba5d61c927a2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22562972"
---
# <a name="rendering-an-attachment-in-rtf-text"></a>以 RTF 文本呈现附件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
Rtf 格式 (RTF)-感知客户端可以通过查看消息的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中下面的转义序列从 RTF 邮件文本检索呈现位置信息：
  
 `\objattph`
  
 **若要找到格式化文本呈现信息**
  
1. 调用**IMessage::GetAttachmentTable**访问邮件的附件表。 有关详细信息，请参阅[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)。
    
2. 构建限制表格行具有**PR_RENDERING_POSITION**不等于-1 的属性限制。 有关详细信息，请参阅**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))。
    
3. 调用**IMAPITable::Restrict**强制实施的限制。 有关详细信息，请参阅[IMAPITable::Restrict](imapitable-restrict.md)。
    
4. 调用**IMAPITable::SortTable**排序附件。 有关详细信息，请参阅[IMAPITable::SortTable](imapitable-sorttable.md)。
    
5. 调用**IMAPITable::QueryRows**检索合适的行。 有关详细信息，请参阅[IMAPITable::QueryRows](imapitable-queryrows.md)。
    
6. 调用消息的**IMAPIProp::OpenProperty**方法，以检索与**IStream**接口**PR_RTF_COMPRESSED** 。 有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)和**PR_RTF_COMPRESSED**。
    
7. 扫描流，呈现占位符中，查找`\objattph`。 关注此占位符的字符是一个已排序的表中的下一个附件。
    

