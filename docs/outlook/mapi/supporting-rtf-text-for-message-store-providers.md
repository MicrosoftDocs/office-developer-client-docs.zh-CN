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
# <a name="supporting-rtf-text-for-message-store-providers"></a><span data-ttu-id="48e18-103">支持邮件存储提供程序的 RTF 文本</span><span class="sxs-lookup"><span data-stu-id="48e18-103">Supporting RTF Text for Message Store Providers</span></span>

  
  
<span data-ttu-id="48e18-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="48e18-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="48e18-105">某些客户端应用程序允许用户在其邮件中使用 rtf 格式文本。</span><span class="sxs-lookup"><span data-stu-id="48e18-105">Some client applications allow users to use Rich Text Format (RTF) text in their messages.</span></span> <span data-ttu-id="48e18-106">如果您的邮件存储区提供程序需要支持邮件中的 RTF 文本, 则除了**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性之外, 还需要处理**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="48e18-106">If your message store provider needs to support RTF text in messages, it needs to handle the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property, in addition to the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property.</span></span> <span data-ttu-id="48e18-107">这主要意味着存储这两个属性, 并确保**PR_BODY**包含**PR_RTF_COMPRESSED**中的文本的纯文本版本。</span><span class="sxs-lookup"><span data-stu-id="48e18-107">Primarily, this means storing both properties, and making sure that **PR_BODY** contains a plain text version of the text in **PR_RTF_COMPRESSED**.</span></span> <span data-ttu-id="48e18-108">[RTFSync](rtfsync.md)函数有助于实现此目的。</span><span class="sxs-lookup"><span data-stu-id="48e18-108">The [RTFSync](rtfsync.md) function is useful for this purpose.</span></span> 
  
<span data-ttu-id="48e18-109">可以在邮件存储对象的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置两个标志, 该属性告知客户端可以从邮件存储提供程序获得的有关**PR_BODY**和 PR_ 的预期内容。 \*\*\*\* 邮件存储区中邮件的 RTF_COMPRESSED 属性。</span><span class="sxs-lookup"><span data-stu-id="48e18-109">There are two flags that can be set in the message store object's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property that tell clients what they can expect from the message store provider with respect to the **PR_BODY** and **PR_RTF_COMPRESSED** properties on messages in the message store.</span></span> <span data-ttu-id="48e18-110">STORE_RTF_OK 标志指示存储区可以从**PR_RTF_COMPRESSED**属性动态生成**PR_BODY**属性的值, 这将缓解客户端不会因显式同步而造成的负担。</span><span class="sxs-lookup"><span data-stu-id="48e18-110">The STORE_RTF_OK flag indicates that the store can generate the value of the **PR_BODY** property from the **PR_RTF_COMPRESSED** property dynamically, which relieves clients from the burden of synchronizing them explicitly.</span></span> <span data-ttu-id="48e18-111">STORE_UNCOMPRESSED_RTF 标志指示邮件存储提供程序可以支持**PR_RTF_COMPRESSED**中的未压缩数据。</span><span class="sxs-lookup"><span data-stu-id="48e18-111">The STORE_UNCOMPRESSED_RTF flag indicates that the message store provider can support uncompressed data in **PR_RTF_COMPRESSED**.</span></span>
  
<span data-ttu-id="48e18-112">不支持 RTF 文本的邮件存储区提供程序需要在**PR_BODY**属性发生更改时删除**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性, 才能与支持 RTF 文本的客户端应用程序正确互操作.</span><span class="sxs-lookup"><span data-stu-id="48e18-112">Message store providers that do not support RTF text need to delete the **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) property when the **PR_BODY** property changes in order to interoperate properly with client applications that do support RTF text.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="48e18-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48e18-113">See also</span></span>



[<span data-ttu-id="48e18-114">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="48e18-114">Message Store Features</span></span>](message-store-features.md)

