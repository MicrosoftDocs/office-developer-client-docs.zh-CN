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
# <a name="supporting-rtf-text-for-message-store-providers"></a><span data-ttu-id="d1109-103">支持邮件存储区提供程序的 RTF 文本</span><span class="sxs-lookup"><span data-stu-id="d1109-103">Supporting RTF Text for Message Store Providers</span></span>

  
  
<span data-ttu-id="d1109-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1109-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1109-105">某些客户端应用程序允许用户在其消息中使用富文本格式 (RTF) 文本。</span><span class="sxs-lookup"><span data-stu-id="d1109-105">Some client applications allow users to use Rich Text Format (RTF) text in their messages.</span></span> <span data-ttu-id="d1109-106">如果您的消息存储提供程序需要在消息中支持 RTF 的文本，它需要处理**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，除了**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d1109-106">If your message store provider needs to support RTF text in messages, it needs to handle the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property, in addition to the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property.</span></span> <span data-ttu-id="d1109-107">主要，这意味着存储这两个属性，并确保**PR_BODY**包含**PR_RTF_COMPRESSED**中的文本的纯文本版本。</span><span class="sxs-lookup"><span data-stu-id="d1109-107">Primarily, this means storing both properties, and making sure that **PR_BODY** contains a plain text version of the text in **PR_RTF_COMPRESSED**.</span></span> <span data-ttu-id="d1109-108">实现此目的， [RTFSync](rtfsync.md)函数很有用。</span><span class="sxs-lookup"><span data-stu-id="d1109-108">The [RTFSync](rtfsync.md) function is useful for this purpose.</span></span> 
  
<span data-ttu-id="d1109-109">有两个标志的告知客户端可以从**PR_BODY**和**PR_ 的消息存储提供程序期望的消息存储对象**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性可设置RTF_COMPRESSED**消息存储库中的邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="d1109-109">There are two flags that can be set in the message store object's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property that tell clients what they can expect from the message store provider with respect to the **PR_BODY** and **PR_RTF_COMPRESSED** properties on messages in the message store.</span></span> <span data-ttu-id="d1109-110">STORE_RTF_OK 标志指示存储可以生成**PR_BODY**属性的值从**PR_RTF_COMPRESSED**属性动态，其减少了对客户端的显式同步其工作负担。</span><span class="sxs-lookup"><span data-stu-id="d1109-110">The STORE_RTF_OK flag indicates that the store can generate the value of the **PR_BODY** property from the **PR_RTF_COMPRESSED** property dynamically, which relieves clients from the burden of synchronizing them explicitly.</span></span> <span data-ttu-id="d1109-111">STORE_UNCOMPRESSED_RTF 标志指示的消息存储提供程序可以支持在**PR_RTF_COMPRESSED**的未压缩的数据。</span><span class="sxs-lookup"><span data-stu-id="d1109-111">The STORE_UNCOMPRESSED_RTF flag indicates that the message store provider can support uncompressed data in **PR_RTF_COMPRESSED**.</span></span>
  
<span data-ttu-id="d1109-112">消息存储提供程序不支持 RTF 的文本的需要删除**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性，当**PR_BODY**属性更改才能正确与客户端应用程序支持 RTF 的文本的互操作.</span><span class="sxs-lookup"><span data-stu-id="d1109-112">Message store providers that do not support RTF text need to delete the **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) property when the **PR_BODY** property changes in order to interoperate properly with client applications that do support RTF text.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d1109-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1109-113">See also</span></span>



[<span data-ttu-id="d1109-114">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="d1109-114">Message Store Features</span></span>](message-store-features.md)

