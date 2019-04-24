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
# <a name="attconversationid-and-attparentid"></a><span data-ttu-id="94b8a-103">attConversationID and attParentID</span><span class="sxs-lookup"><span data-stu-id="94b8a-103">attConversationID and attParentID</span></span>

<span data-ttu-id="94b8a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="94b8a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="94b8a-105">Windows for 工作组3.1 邮件对话项是文本字符串。</span><span class="sxs-lookup"><span data-stu-id="94b8a-105">The Windows for Workgroups 3.1 Mail conversation key is a text string.</span></span> <span data-ttu-id="94b8a-106">等效的 MAPI 是一个二进制值。</span><span class="sxs-lookup"><span data-stu-id="94b8a-106">The MAPI equivalent is a binary value.</span></span> <span data-ttu-id="94b8a-107">为了提供向后兼容性, TNEF 实现将二进制数据转换为文本并添加一个终止的 null 字符。</span><span class="sxs-lookup"><span data-stu-id="94b8a-107">To provide backward compatibility, the TNEF implementation converts the binary data to text and adds a terminating null character.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94b8a-108">MAPI 中这些 TNEF 属性映射到的相应属性 (PR_CONVERSATION_KEY 和 PR_PARENT_KEY) 在 Microsoft Exchange Server 中已被弃用: 使用**PR_CONVERSATION_KEY**的[PidTagConversationKey 规范属性](pidtagconversationkey-canonical-property.md), 仅在 Outlook 中保持, 以查找**IPM。MessageManager**邮件。</span><span class="sxs-lookup"><span data-stu-id="94b8a-108">The corresponding properties in MAPI to which these TNEF attributes are mapped, PR_CONVERSATION_KEY and PR_PARENT_KEY, have been deprecated in Microsoft Exchange Server: Use of **PR_CONVERSATION_KEY**, the [PidTagConversationKey Canonical Property](pidtagconversationkey-canonical-property.md), persists in Outlook only, for locating **IPM.MessageManager** messages.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="94b8a-109">注解</span><span class="sxs-lookup"><span data-stu-id="94b8a-109">Remarks</span></span>

<span data-ttu-id="94b8a-110">**PR_CONVERSATION_KEY**属性是其他过时的 precursor **PR_CONVERSATION_INDEX**, [PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)和**PR_CONVERSATION_TOPIC**, [PidTagConversationTopic 规范](pidtagconversationtopic-canonical-property.md)应改用的属性。</span><span class="sxs-lookup"><span data-stu-id="94b8a-110">The **PR_CONVERSATION_KEY** property is the otherwise obsolete precursor of the **PR_CONVERSATION_INDEX**, [PidTagConversationIndex Canonical Property](pidtagconversationindex-canonical-property.md) and **PR_CONVERSATION_TOPIC**, [PidTagConversationTopic Canonical Property](pidtagconversationtopic-canonical-property.md), which should be used instead.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="94b8a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94b8a-111">See also</span></span>

- [<span data-ttu-id="94b8a-112">IPM 子树</span><span class="sxs-lookup"><span data-stu-id="94b8a-112">IPM Subtree</span></span>](ipm-subtree.md)
- [<span data-ttu-id="94b8a-113">MAPI 特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="94b8a-113">MAPI Special Folders</span></span>](mapi-special-folders.md)

