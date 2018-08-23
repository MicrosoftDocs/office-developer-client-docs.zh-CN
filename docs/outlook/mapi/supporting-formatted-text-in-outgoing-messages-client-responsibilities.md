---
title: 支持在传出邮件客户端责任的带格式的文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7238b1a9-01ed-46a0-a625-26763323317d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 975dd172b6ad342351f014d0966d62a150f713c6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571288"
---
# <a name="supporting-formatted-text-in-outgoing-messages-client-responsibilities"></a><span data-ttu-id="44a08-103">支持待发邮件中的格式化文本：客户端责任</span><span class="sxs-lookup"><span data-stu-id="44a08-103">Supporting Formatted Text in Outgoing Messages: Client Responsibilities</span></span>

  
  
<span data-ttu-id="44a08-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="44a08-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="44a08-105">客户端应用程序设置的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性、 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性或的传出消息的**PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="44a08-105">Client applications set the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property, the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property, or the **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) property for an outgoing message.</span></span> <span data-ttu-id="44a08-106">仅支持纯文本的客户端设置仅**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="44a08-106">Clients that support only plain text set only the **PR_BODY** property.</span></span> <span data-ttu-id="44a08-107">Rtf 格式 (RTF)-请注意，客户端可能将**PR_BODY**和**PR_RTF_COMPRESSED**属性，或者仅**PR_RTF_COMPRESSED**，具体取决于消息存储提供程序正在使用。</span><span class="sxs-lookup"><span data-stu-id="44a08-107">Rich Text Format (RTF)-aware clients might set both **PR_BODY** and **PR_RTF_COMPRESSED** properties, or only **PR_RTF_COMPRESSED**, depending on the message store provider being used.</span></span> <span data-ttu-id="44a08-108">HTML 感知客户端设置**PR_HTML**属性。</span><span class="sxs-lookup"><span data-stu-id="44a08-108">HTML-aware clients set the **PR_HTML** property.</span></span> 
  
<span data-ttu-id="44a08-109">非常重要的检查其消息存储库**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性以确定是否的存储支持 RTF 的客户端。</span><span class="sxs-lookup"><span data-stu-id="44a08-109">It is important for a client to check its message store's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property to determine whether the store supports RTF.</span></span> <span data-ttu-id="44a08-110">如果消息存储不是 RTF 感知的 RTF 感知客户端设置为每个传出消息的**PR_BODY**和**PR_RTF_COMPRESSED**属性。</span><span class="sxs-lookup"><span data-stu-id="44a08-110">If the message store is not RTF-aware, an RTF-aware client sets both the **PR_BODY** and **PR_RTF_COMPRESSED** properties for each outgoing message.</span></span> 
  
<span data-ttu-id="44a08-111">如果消息存储为 RTF 感知的仅将**PR_RTF_COMPRESSED**属性需要设置。</span><span class="sxs-lookup"><span data-stu-id="44a08-111">If the message store is RTF-aware, only the **PR_RTF_COMPRESSED** property needs to be set.</span></span> 
  
 <span data-ttu-id="44a08-112">**若要设置 PR_RTF_COMPRESSED 并确保同步过程在发生作为有必要，RTF 感知客户端**</span><span class="sxs-lookup"><span data-stu-id="44a08-112">**To set PR_RTF_COMPRESSED and ensure that the synchronization process occurs as necessary, RTF-aware clients**</span></span>
  
1. <span data-ttu-id="44a08-113">调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法以打开**PR_RTF_COMPRESSED**属性，设置的 MAPI_CREATE 和 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="44a08-113">Call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_RTF_COMPRESSED** property, setting both the MAPI_CREATE and MAPI_MODIFY flags.</span></span> <span data-ttu-id="44a08-114">MAPI_CREATE 确保新的任何数据替换任何旧数据和 MAPI_MODIFY 使您能够进行这些替换。</span><span class="sxs-lookup"><span data-stu-id="44a08-114">MAPI_CREATE ensures that any new data replaces any old data and MAPI_MODIFY enables you to make those replacements.</span></span> 
    
2. <span data-ttu-id="44a08-115">调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数，如果消息存储在其**PR_STORE_SUPPORT_MASK**属性，以获取**PR_RTF_COMPRESSED 未压缩的版本中设置 STORE_UNCOMPRESSED_RTF 位传递 STORE_UNCOMPRESSED_RTF**从**OpenProperty**返回流。</span><span class="sxs-lookup"><span data-stu-id="44a08-115">Call the [WrapCompressedRTFStream](wrapcompressedrtfstream.md) function, passing STORE_UNCOMPRESSED_RTF if the message store sets the STORE_UNCOMPRESSED_RTF bit in its **PR_STORE_SUPPORT_MASK** property, to get an uncompressed version of the **PR_RTF_COMPRESSED** stream returned from **OpenProperty**.</span></span>
    
3. <span data-ttu-id="44a08-116">写入到未压缩流**WrapCompressedRTFStream**从返回的消息文本数据。</span><span class="sxs-lookup"><span data-stu-id="44a08-116">Write the message text data to the uncompressed stream returned from **WrapCompressedRTFStream**.</span></span>
    
4. <span data-ttu-id="44a08-117">提交并释放未压缩和压缩流。</span><span class="sxs-lookup"><span data-stu-id="44a08-117">Commit and release both the uncompressed and compressed streams.</span></span>
    
<span data-ttu-id="44a08-118">此时，消息存储提供程序支持 RTF，如果您已完成所有必需的。</span><span class="sxs-lookup"><span data-stu-id="44a08-118">At this point, if the message store provider supports RTF, you have done all that is required.</span></span> <span data-ttu-id="44a08-119">如有必要，可以依赖处理同步过程和**PR_BODY**属性中，创建消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="44a08-119">You can depend on the message store provider to handle the synchronization process and the creation of the **PR_BODY** property, if necessary.</span></span> <span data-ttu-id="44a08-120">但是，如果消息存储提供程序不支持 RTF，您必须调用[RTFSync](rtfsync.md)函数同步带格式的文本设置 RTF_SYNC_RTF_CHANGED 标志。</span><span class="sxs-lookup"><span data-stu-id="44a08-120">However, if the message store provider does not support RTF, you must call the [RTFSync](rtfsync.md) function to synchronize the text with the formatting, setting the RTF_SYNC_RTF_CHANGED flag.</span></span> 
  

