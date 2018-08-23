---
title: 支持邮件存储区提供程序的 RTF 文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0022fe70-cf11-49a5-9c97-a6bc5b5b13aa
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3e65ebd3ea485ca54978d622e8aaf093dc5eff74
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594066"
---
# <a name="supporting-rtf-text-for-message-store-providers"></a>支持邮件存储区提供程序的 RTF 文本

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
某些客户端应用程序允许用户在其消息中使用富文本格式 (RTF) 文本。 如果您的消息存储提供程序需要在消息中支持 RTF 的文本，它需要处理**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，除了**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。 主要，这意味着存储这两个属性，并确保**PR_BODY**包含**PR_RTF_COMPRESSED**中的文本的纯文本版本。 实现此目的， [RTFSync](rtfsync.md)函数很有用。 
  
有两个标志的告知客户端可以从**PR_BODY**和**PR_ 的消息存储提供程序期望的消息存储对象**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性可设置RTF_COMPRESSED**消息存储库中的邮件的属性。 STORE_RTF_OK 标志指示存储可以生成**PR_BODY**属性的值从**PR_RTF_COMPRESSED**属性动态，其减少了对客户端的显式同步其工作负担。 STORE_UNCOMPRESSED_RTF 标志指示的消息存储提供程序可以支持在**PR_RTF_COMPRESSED**的未压缩的数据。
  
消息存储提供程序不支持 RTF 的文本的需要删除**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性，当**PR_BODY**属性更改才能正确与客户端应用程序支持 RTF 的文本的互操作. 
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

