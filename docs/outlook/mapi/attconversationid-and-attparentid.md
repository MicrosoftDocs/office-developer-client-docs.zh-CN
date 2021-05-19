---
title: attConversationID and attParentID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bed36900-e44d-434b-a4f2-d10f2d6f70da
description: 上次修改时间：2013 年 3 月 12 日
ms.openlocfilehash: c5880aefe7c2dba2e5e4c5405aae2020bb86c711
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410047"
---
# <a name="attconversationid-and-attparentid"></a>attConversationID and attParentID

**适用于**：Outlook 2013 | Outlook 2016 
  
工作组Windows 3.1 邮件对话键的字符串是文本字符串。 MAPI 等效值是二进制值。 为了提供向后兼容性，TNEF 实现将二进制数据转换为文本并添加终止 null 字符。
  
> [!NOTE]
> 这些 TNEF 属性映射到的 MAPI、PR_CONVERSATION_KEY 和 PR_PARENT_KEY 中的相应属性已在 Microsoft Exchange Server 中弃用：使用 **PR_CONVERSATION_KEY（**[即 PidTagConversationKey](pidtagconversationkey-canonical-property.md)规范属性）仅保留于 Outlook 中，用于定位 **IPM。MessageManager** 邮件。 
  
## <a name="remarks"></a>备注

PR_CONVERSATION_KEY **属性** 是 PR_CONVERSATION_INDEX [、PidTagConversationIndex](pidtagconversationindex-canonical-property.md)规范属性和 **PR_CONVERSATION_TOPIC** [、PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)规范属性（应改为使用）的过时前兆。 
  
## <a name="see-also"></a>另请参阅

- [IPM 子树](ipm-subtree.md)
- [MAPI 特殊文件夹](mapi-special-folders.md)

