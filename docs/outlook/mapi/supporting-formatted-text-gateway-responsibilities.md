---
title: 支持格式化的文本网关职责
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: de737118-5f3b-464f-b036-f4a3489d411a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d5c3480018be399a85ee0bfda7ce1ff9b701cecc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327417"
---
# <a name="supporting-formatted-text-gateway-responsibilities"></a>支持格式化文本: 网关责任

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **处理传出邮件的 rtf 格式、网关**
  
1. 仅检索邮件存储区中的邮件的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。 仅检索**PR_RTF_COMPRESSED**属性的主要优势在于, 如果网关和邮件存储在不同的计算机上存在, 则不需要在计算机之间发送邮件文本。 
    
2. 通过调用 RTF 库函数**HrTextFromCompressedRTFStream**或 (如果该邮件在本地存储, 则为**RTFSync**) 从格式化文本生成邮件文本。 应在对**RTFSync**的调用中设置 RTF_SYNC_RTF_CHANGED 标志。 有关详细信息, 请参阅[RTFSync](rtfsync.md)。
    
3. 对邮件文本进行任何不可恢复的修改, 如丢弃不受支持的字符。 
    
4. 确保**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 和所有 RTF auxilliary 属性均已设置或不存在。
    
5. 如果进行了任何修改, 则调用**RTFSync**同时设置 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED 标志。 **RTFSync**将从修改的文本中重新计算 RTF auxilliary 属性。 
    
6. 对邮件文本进行任何 reversable 修改, 如插入附件占位符和执行非破坏性的代码页转换。
    
7. 发送邮件。
    
 **处理传入邮件的 rtf 格式、网关**
  
1. 对发送邮件之前直接进行的任何邮件文本修改进行反向操作。 
    
2. 如果邮件同时包含**PR_RTF_COMPRESSED**和**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性, 请调用**RTFSync** 。 
    
3. 如果邮件中包含 PR_RTF_COMPRESSED 属性, 请使用 " **** " 属性更新邮件存储区中的邮件;仅当**PR_RTF_COMPRESSED**不存在时, 使用**PR_BODY**属性进行更新。 
    
4. 如果邮件同时包含此属性和**PR_RTF_COMPRESSED**, 则丢弃**PR_BODY** 。
    
如果邮件存储在不同的计算机上, 网关将调用**RTFSync**以避免传输邮件文本和带格式的文本。 如果网关是本地的, 则可以同时设置这两个属性, 并允许邮件存储区执行同步。 
  

