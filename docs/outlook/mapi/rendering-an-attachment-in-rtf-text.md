---
title: 在 RTF 文本中呈现附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 26372539-e9fe-464d-95c7-90b58c20b98f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b2a1a23f073d05e85c8203826e3407c5ae193f19
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280357"
---
# <a name="rendering-an-attachment-in-rtf-text"></a>在 RTF 文本中呈现附件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
rtf 格式 (rtf) 感知客户端可以通过在邮件的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中查找以下转义序列来检索 RTF 邮件文本中的呈现位置信息:
  
 `\objattph`
  
 **在格式化文本中查找呈现信息**
  
1. 调用**IMessage:: GetAttachmentTable**以访问邮件的附件表。 有关详细信息, 请参阅[IMessage:: GetAttachmentTable](imessage-getattachmenttable.md)。
    
2. 生成将表限制为**PR_RENDERING_POSITION**不等于-1 的行的属性限制。 有关详细信息, 请参阅**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))。
    
3. 调用**IMAPITable:: Restrict**以强制实施限制。 有关详细信息, 请参阅[IMAPITable:: Restrict](imapitable-restrict.md)。
    
4. 调用**IMAPITable:: SortTable**对附件进行排序。 有关详细信息, 请参阅[IMAPITable:: SortTable](imapitable-sorttable.md)。
    
5. 调用**IMAPITable:: QueryRows**以检索相应的行。 有关详细信息, 请参阅[IMAPITable:: QueryRows](imapitable-queryrows.md)。
    
6. 调用邮件的**IMAPIProp:: OpenProperty**方法, 以使用**IStream**接口检索**PR_RTF_COMPRESSED** 。 有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**。
    
7. 扫描流, 查找呈现占位符`\objattph`。 此占位符后面的字符是排序表中下一个附件的位置。
    

