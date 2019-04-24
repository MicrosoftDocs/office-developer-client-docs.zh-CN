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
# <a name="supporting-formatted-text-gateway-responsibilities"></a><span data-ttu-id="60479-103">支持格式化文本: 网关责任</span><span class="sxs-lookup"><span data-stu-id="60479-103">Supporting Formatted Text: Gateway Responsibilities</span></span>

  
  
<span data-ttu-id="60479-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="60479-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="60479-105">**处理传出邮件的 rtf 格式、网关**</span><span class="sxs-lookup"><span data-stu-id="60479-105">**To handle Rich Text Format for outgoing messages, gateways**</span></span>
  
1. <span data-ttu-id="60479-106">仅检索邮件存储区中的邮件的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="60479-106">Retrieve only a message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property from the message store.</span></span> <span data-ttu-id="60479-107">仅检索**PR_RTF_COMPRESSED**属性的主要优势在于, 如果网关和邮件存储在不同的计算机上存在, 则不需要在计算机之间发送邮件文本。</span><span class="sxs-lookup"><span data-stu-id="60479-107">The main advantage in retrieving only the **PR_RTF_COMPRESSED** property is that the message text does not need to be sent between machines if the gateway and the message store exist on different machines.</span></span> 
    
2. <span data-ttu-id="60479-108">通过调用 RTF 库函数**HrTextFromCompressedRTFStream**或 (如果该邮件在本地存储, 则为**RTFSync**) 从格式化文本生成邮件文本。</span><span class="sxs-lookup"><span data-stu-id="60479-108">Generate the message text from the formatted text either by calling the RTF library function **HrTextFromCompressedRTFStream** or, if the message is stored locally, **RTFSync**.</span></span> <span data-ttu-id="60479-109">应在对**RTFSync**的调用中设置 RTF_SYNC_RTF_CHANGED 标志。</span><span class="sxs-lookup"><span data-stu-id="60479-109">The RTF_SYNC_RTF_CHANGED flag should be set in the call to **RTFSync**.</span></span> <span data-ttu-id="60479-110">有关详细信息, 请参阅[RTFSync](rtfsync.md)。</span><span class="sxs-lookup"><span data-stu-id="60479-110">For more information, see [RTFSync](rtfsync.md).</span></span>
    
3. <span data-ttu-id="60479-111">对邮件文本进行任何不可恢复的修改, 如丢弃不受支持的字符。</span><span class="sxs-lookup"><span data-stu-id="60479-111">Make any irreversible modifications to the message text, such as dropping unsupported characters.</span></span> 
    
4. <span data-ttu-id="60479-112">确保**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 和所有 RTF auxilliary 属性均已设置或不存在。</span><span class="sxs-lookup"><span data-stu-id="60479-112">Ensure that both **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) and all of the RTF auxilliary properties are either set or absent.</span></span>
    
5. <span data-ttu-id="60479-113">如果进行了任何修改, 则调用**RTFSync**同时设置 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED 标志。</span><span class="sxs-lookup"><span data-stu-id="60479-113">If any modifications were made, call **RTFSync** with both the RTF_SYNC_RTF_CHANGED and RTF_SYNC_BODY_CHANGED flags set.</span></span> <span data-ttu-id="60479-114">**RTFSync**将从修改的文本中重新计算 RTF auxilliary 属性。</span><span class="sxs-lookup"><span data-stu-id="60479-114">**RTFSync** will recalculate the RTF auxilliary properties from the modified text.</span></span> 
    
6. <span data-ttu-id="60479-115">对邮件文本进行任何 reversable 修改, 如插入附件占位符和执行非破坏性的代码页转换。</span><span class="sxs-lookup"><span data-stu-id="60479-115">Make any reversable modifications to the message text, such as inserting attachment placeholders and performing nondestructive code page conversions.</span></span>
    
7. <span data-ttu-id="60479-116">发送邮件。</span><span class="sxs-lookup"><span data-stu-id="60479-116">Send the message.</span></span>
    
 <span data-ttu-id="60479-117">**处理传入邮件的 rtf 格式、网关**</span><span class="sxs-lookup"><span data-stu-id="60479-117">**To handle Rich Text Format for incoming messages, gateways**</span></span>
  
1. <span data-ttu-id="60479-118">对发送邮件之前直接进行的任何邮件文本修改进行反向操作。</span><span class="sxs-lookup"><span data-stu-id="60479-118">Reverse any message text modifications that were made directly before the message was sent.</span></span> 
    
2. <span data-ttu-id="60479-119">如果邮件同时包含**PR_RTF_COMPRESSED**和**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性, 请调用**RTFSync** 。</span><span class="sxs-lookup"><span data-stu-id="60479-119">Call **RTFSync** if the message contains both the **PR_RTF_COMPRESSED** and **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) properties.</span></span> 
    
3. <span data-ttu-id="60479-120">如果邮件中包含 PR_RTF_COMPRESSED 属性, 请使用 " \*\*\*\* " 属性更新邮件存储区中的邮件;仅当**PR_RTF_COMPRESSED**不存在时, 使用**PR_BODY**属性进行更新。</span><span class="sxs-lookup"><span data-stu-id="60479-120">Update the message in the message store with the **PR_RTF_COMPRESSED** property if the message contains it; update with the **PR_BODY** property only if **PR_RTF_COMPRESSED** is absent.</span></span> 
    
4. <span data-ttu-id="60479-121">如果邮件同时包含此属性和**PR_RTF_COMPRESSED**, 则丢弃**PR_BODY** 。</span><span class="sxs-lookup"><span data-stu-id="60479-121">Discard **PR_BODY** if the message contains both this property and **PR_RTF_COMPRESSED**.</span></span>
    
<span data-ttu-id="60479-122">如果邮件存储在不同的计算机上, 网关将调用**RTFSync**以避免传输邮件文本和带格式的文本。</span><span class="sxs-lookup"><span data-stu-id="60479-122">Gateways call **RTFSync** to avoid transmitting both the message text and formatted text if the message store is on a different machine.</span></span> <span data-ttu-id="60479-123">如果网关是本地的, 则可以同时设置这两个属性, 并允许邮件存储区执行同步。</span><span class="sxs-lookup"><span data-stu-id="60479-123">If the gateway is local, it can set both properties and allow the message store to perform the synchronization.</span></span> 
  

