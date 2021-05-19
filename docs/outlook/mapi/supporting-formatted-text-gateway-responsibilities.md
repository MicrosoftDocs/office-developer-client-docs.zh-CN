---
title: 支持格式化文本网关责任
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: de737118-5f3b-464f-b036-f4a3489d411a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d5c3480018be399a85ee0bfda7ce1ff9b701cecc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419427"
---
# <a name="supporting-formatted-text-gateway-responsibilities"></a>支持格式化文本：网关责任

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **处理传出邮件的富文本格式，网关**
  
1. 从邮件存储中仅检索 **PR_RTF_COMPRESSED (** [PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。 仅检索 PR_RTF_COMPRESSED 属性的主要优点是，如果网关和邮件存储存在于不同的计算机上，则无需在计算机之间发送消息文本。 
    
2. 通过调用 RTF 库函数 **HrTextFromCompressedRTFStream** 或 **RTFSync（** 如果邮件存储在本地）从格式化文本生成消息文本。 应在RTF_SYNC_RTF_CHANGED **RTFSync** 中设置该标记。 有关详细信息，请参阅 [RTFSync](rtfsync.md)。
    
3. 对邮件文本进行任何不可恢复的修改，例如删除不受支持的字符。 
    
4. 确保[PidTagRtfInSync PR_RTF_IN_SYNC (PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 所有 RTF 辅助属性已设置或不存在。 
    
5. 如果进行了任何修改，请调用同时设置了 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED **RTFSync。** **RTFSync** 将重新计算修改文本中的 RTF 辅助属性。 
    
6. 对邮件文本进行任何可还原的修改，例如插入附件占位符和执行无损坏的代码页转换。
    
7. 发送邮件。
    
 **处理传入邮件、网关的富文本格式**
  
1. 取消直接在邮件发送前所做的任何邮件文本修改。 
    
2. 如果邮件包含 [PidTagBody](pidtagbody-canonical-property.md)属性中的 PR_RTF_COMPRESSED **和** PR_BODY **(，)** **RTFSync。** 
    
3. 使用 PR_RTF_COMPRESSED **属性更新** 邮件存储中的邮件;仅在缺少 **PR_BODY** **时PR_RTF_COMPRESSED更新** 。 
    
4. 如果 **PR_BODY** 包含此属性和属性，则放弃 **PR_RTF_COMPRESSED。**
    
网关调用 **RTFSync** 以避免在邮件存储位于其他计算机上时同时传输消息文本和格式化文本。 如果网关是本地网关，它可以同时设置这两个属性并允许邮件存储执行同步。 
  

