---
title: 支持格式化的文本网关职责
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: de737118-5f3b-464f-b036-f4a3489d411a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6d2c85aa76a372ba79e55dbf5b22024288214df6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778909"
---
# <a name="supporting-formatted-text-gateway-responsibilities"></a>支持格式化文本：网关责任

  
  
**适用于**： Outlook 
  
 **若要处理的传出邮件，网关的富文本格式**
  
1. 从邮件存储检索仅消息的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。 检索仅**PR_RTF_COMPRESSED**属性中的主要优点是消息文本不需要发送计算机之间，如果不同的计算机上存在的网关和消息存储库。 
    
2. 可通过调用 RTF 库函数**HrTextFromCompressedRTFStream**格式化文本从生成的消息文本或，如果邮件存储在本地， **RTFSync**。 应将 RTF_SYNC_RTF_CHANGED 标志设置对**RTFSync**的调用中。 有关详细信息，请参阅[RTFSync](rtfsync.md)。
    
3. 任何不可逆转地对进行修改的消息文本，如删除不支持的字符。 
    
4. 确保**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 和所有 RTF 辅助属性进行设置，或不存在。
    
5. 如果做任何修改，调用**RTFSync**的 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED 标志设置。 **RTFSync**将重新计算的已修改的文本中的 RTF 辅助属性。 
    
6. 任何可撤销对进行修改的消息文本，如插入附件占位符和执行破坏性的代码页转换。
    
7. 发送消息。
    
 **若要处理的传入邮件，网关的富文本格式**
  
1. 还原之前已发送邮件直接进行任何消息文本进行修改。 
    
2. 如果邮件包含的**PR_RTF_COMPRESSED**和**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，请调用**RTFSync** 。 
    
3. 如果邮件包含; 使用**PR_RTF_COMPRESSED**属性更新消息存储库中的消息更新**PR_BODY**属性才**PR_RTF_COMPRESSED**不存在。 
    
4. 如果邮件包含此属性和**PR_RTF_COMPRESSED**，放弃**PR_BODY** 。
    
网关呼叫**RTFSync**来避免传输的消息文本和格式化的文本，如果消息存储是不同的计算机上。 如果本地网关，它可以设置这两个属性，并允许的邮件存储来执行同步。 
  

