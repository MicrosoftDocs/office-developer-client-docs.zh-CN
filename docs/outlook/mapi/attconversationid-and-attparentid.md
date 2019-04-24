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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318415"
---
# <a name="attconversationid-and-attparentid"></a>attConversationID and attParentID

**适用于**：Outlook 2013 | Outlook 2016 
  
Windows for 工作组3.1 邮件对话项是文本字符串。 等效的 MAPI 是一个二进制值。 为了提供向后兼容性, TNEF 实现将二进制数据转换为文本并添加一个终止的 null 字符。
  
> [!NOTE]
> MAPI 中这些 TNEF 属性映射到的相应属性 (PR_CONVERSATION_KEY 和 PR_PARENT_KEY) 在 Microsoft Exchange Server 中已被弃用: 使用**PR_CONVERSATION_KEY**的[PidTagConversationKey 规范属性](pidtagconversationkey-canonical-property.md), 仅在 Outlook 中保持, 以查找**IPM。MessageManager**邮件。 
  
## <a name="remarks"></a>注解

**PR_CONVERSATION_KEY**属性是其他过时的 precursor **PR_CONVERSATION_INDEX**, [PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)和**PR_CONVERSATION_TOPIC**, [PidTagConversationTopic 规范](pidtagconversationtopic-canonical-property.md)应改用的属性。
  
## <a name="see-also"></a>另请参阅

- [IPM 子树](ipm-subtree.md)
- [MAPI 特殊文件夹](mapi-special-folders.md)

