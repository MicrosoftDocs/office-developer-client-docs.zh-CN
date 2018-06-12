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
# <a name="attconversationid-and-attparentid"></a><span data-ttu-id="d11ae-103">attConversationID 和 attParentID</span><span class="sxs-lookup"><span data-stu-id="d11ae-103">attConversationID and attParentID</span></span>

<span data-ttu-id="d11ae-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d11ae-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d11ae-105">工作组 3.1 邮件对话键 Windows 是一个文本字符串。</span><span class="sxs-lookup"><span data-stu-id="d11ae-105">The Windows for Workgroups 3.1 Mail conversation key is a text string.</span></span> <span data-ttu-id="d11ae-106">MAPI 等同于二进制值。</span><span class="sxs-lookup"><span data-stu-id="d11ae-106">The MAPI equivalent is a binary value.</span></span> <span data-ttu-id="d11ae-107">若要提供向后兼容性，TNEF 实现将二进制数据转换为文本，并添加终止空字符。</span><span class="sxs-lookup"><span data-stu-id="d11ae-107">To provide backward compatibility, the TNEF implementation converts the binary data to text and adds a terminating null character.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d11ae-108">MAPI 中的相应属性这些 TNEF 属性都映射到，PR_CONVERSATION_KEY 和 PR_PARENT_KEY 中, 已弃用 Microsoft Exchange Server： 利用**PR_CONVERSATION_KEY**，PidTagConversationKey 规范[属性](pidtagconversationkey-canonical-property.md)，在 Outlook 中仅，用于查找**IPM 保持。MessageManager**消息。</span><span class="sxs-lookup"><span data-stu-id="d11ae-108">The corresponding properties in MAPI to which these TNEF attributes are mapped, PR_CONVERSATION_KEY and PR_PARENT_KEY, have been deprecated in Microsoft Exchange Server: Use of **PR_CONVERSATION_KEY**, the [PidTagConversationKey Canonical Property](pidtagconversationkey-canonical-property.md), persists in Outlook only, for locating **IPM.MessageManager** messages.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="d11ae-109">备注</span><span class="sxs-lookup"><span data-stu-id="d11ae-109">Remarks</span></span>

<span data-ttu-id="d11ae-110">**PR_CONVERSATION_KEY**属性是**PR_CONVERSATION_INDEX**、 [PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)和**PR_CONVERSATION_TOPIC**， [PidTagConversationTopic 规范的否则为过时的前提属性](pidtagconversationtopic-canonical-property.md)，而是应使用哪些。</span><span class="sxs-lookup"><span data-stu-id="d11ae-110">The **PR_CONVERSATION_KEY** property is the otherwise obsolete precursor of the **PR_CONVERSATION_INDEX**, [PidTagConversationIndex Canonical Property](pidtagconversationindex-canonical-property.md) and **PR_CONVERSATION_TOPIC**, [PidTagConversationTopic Canonical Property](pidtagconversationtopic-canonical-property.md), which should be used instead.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d11ae-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d11ae-111">See also</span></span>

- [<span data-ttu-id="d11ae-112">IPM 子树</span><span class="sxs-lookup"><span data-stu-id="d11ae-112">IPM Subtree</span></span>](ipm-subtree.md)
- [<span data-ttu-id="d11ae-113">MAPI 特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="d11ae-113">MAPI Special Folders</span></span>](mapi-special-folders.md)

