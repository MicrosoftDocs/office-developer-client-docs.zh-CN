---
title: 支持邮件存储提供程序的 RTF 文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0022fe70-cf11-49a5-9c97-a6bc5b5b13aa
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: dc1d8a5e237b7b34f3a57e9789e03e2f16237764
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414212"
---
# <a name="supporting-rtf-text-for-message-store-providers"></a>支持邮件存储提供程序的 RTF 文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些客户端应用程序允许用户在其邮件中使用 rtf 格式文本。 如果您的邮件存储区提供程序需要支持邮件中的 RTF 文本, 则除了**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性之外, 还需要处理**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。 这主要意味着存储这两个属性, 并确保**PR_BODY**包含**PR_RTF_COMPRESSED**中的文本的纯文本版本。 [RTFSync](rtfsync.md)函数有助于实现此目的。 
  
可以在邮件存储对象的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置两个标志, 该属性告知客户端可以从邮件存储提供程序获得的有关**PR_BODY**和 PR_ 的预期内容。 **** 邮件存储区中邮件的 RTF_COMPRESSED 属性。 STORE_RTF_OK 标志指示存储区可以从**PR_RTF_COMPRESSED**属性动态生成**PR_BODY**属性的值, 这将缓解客户端不会因显式同步而造成的负担。 STORE_UNCOMPRESSED_RTF 标志指示邮件存储提供程序可以支持**PR_RTF_COMPRESSED**中的未压缩数据。
  
不支持 RTF 文本的邮件存储区提供程序需要在**PR_BODY**属性发生更改时删除**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性, 才能与支持 RTF 文本的客户端应用程序正确互操作. 
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

