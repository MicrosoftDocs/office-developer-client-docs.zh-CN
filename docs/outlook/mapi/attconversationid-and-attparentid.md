---
title: attConversationID 和 attParentID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bed36900-e44d-434b-a4f2-d10f2d6f70da
description: 上次修改时间： 2013 年 3 月 12 日
ms.openlocfilehash: 2fd3e66e3171c677465a533ede3001cd0b28c8aa
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774567"
---
# <a name="attconversationid-and-attparentid"></a>attConversationID 和 attParentID

**适用于**： Outlook 
  
工作组 3.1 邮件对话键 Windows 是一个文本字符串。 MAPI 等同于二进制值。 若要提供向后兼容性，TNEF 实现将二进制数据转换为文本，并添加终止空字符。
  
> [!NOTE]
> MAPI 中的相应属性这些 TNEF 属性都映射到，PR_CONVERSATION_KEY 和 PR_PARENT_KEY 中, 已弃用 Microsoft Exchange Server： 利用**PR_CONVERSATION_KEY**，PidTagConversationKey 规范[属性](pidtagconversationkey-canonical-property.md)，在 Outlook 中仅，用于查找**IPM 保持。MessageManager**消息。 
  
## <a name="remarks"></a>备注

**PR_CONVERSATION_KEY**属性是**PR_CONVERSATION_INDEX**、 [PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)和**PR_CONVERSATION_TOPIC**， [PidTagConversationTopic 规范的否则为过时的前提属性](pidtagconversationtopic-canonical-property.md)，而是应使用哪些。
  
## <a name="see-also"></a>另请参阅

- [IPM 子树](ipm-subtree.md)
- [MAPI 特殊文件夹](mapi-special-folders.md)

