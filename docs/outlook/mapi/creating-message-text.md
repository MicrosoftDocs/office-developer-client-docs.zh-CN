---
title: 创建消息文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 70d1fb24-91a9-4043-8c9d-be1523012e6b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 38be3bc2df8931ca45da12e43436377545e8a977
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774757"
---
# <a name="creating-message-text"></a><span data-ttu-id="ebeb5-103">创建消息文本</span><span class="sxs-lookup"><span data-stu-id="ebeb5-103">Creating message text</span></span>

<span data-ttu-id="ebeb5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ebeb5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ebeb5-105">尽管某些消息组成的 nothing 比收件人列表和主题行，大多数消息，专门 IPM 的内容。注意邮件，包含文本。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-105">Although some messages are made up of nothing more than a recipient list and a subject line, the content of most messages, specifically IPM.Note messages, includes text.</span></span> <span data-ttu-id="ebeb5-106">消息文本可为纯文本或格式，并存储在三个属性： **PR\_正文**([PidTagBody](pidtagbody-canonical-property.md))， **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-106">Message text can be plain or formatted and is stored in three properties: **PR\_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), and **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> 

<span data-ttu-id="ebeb5-107">如果您的客户端，基于纯文本设置**PR\_正文**。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-107">If your client is plain text-based, set **PR\_BODY**.</span></span> <span data-ttu-id="ebeb5-108">如果您支持格式化的文本富文本格式 (RTF) 中，设置仅**PR_RTF_COMPRESSED**或两个**PR_RTF_COMPRESSED**和**PR\_正文**，这取决于您使用的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-108">If you support formatted text in the Rich Text Format (RTF), set either **PR_RTF_COMPRESSED** only or both **PR_RTF_COMPRESSED** and **PR\_BODY**, depending on the message store provider that you are using.</span></span> <span data-ttu-id="ebeb5-109">时的 RTF 感知客户端使用的为 RTF 感知的邮件存储区，仅设置**PR_RTF_COMPRESSED** 。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-109">When an RTF-aware client is using an RTF-aware message store, it sets **PR_RTF_COMPRESSED** only.</span></span> <span data-ttu-id="ebeb5-110">RTF 感知客户端使用的非 RTF 注意消息存储，将这两个属性。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-110">When an RTF-aware client is using a non-RTF-aware message store, it sets both properties.</span></span> <span data-ttu-id="ebeb5-111">如果您的客户端支持 HTML，设置**PR_HTML**属性。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-111">If your client supports HTML, set the **PR_HTML** property.</span></span> 
  
## <a name="determine-whether-your-message-store-supports-rich-text-format"></a><span data-ttu-id="ebeb5-112">确定您的消息存储是否支持富文本格式</span><span class="sxs-lookup"><span data-stu-id="ebeb5-112">Determine whether your message store supports Rich Text Format</span></span>
  
1. <span data-ttu-id="ebeb5-113">调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-113">Call the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span>
    
2. <span data-ttu-id="ebeb5-114">检查 STORE_RTF_OK 位。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-114">Check for the STORE_RTF_OK bit.</span></span> <span data-ttu-id="ebeb5-115">如果设置 STORE_RTF_OK，消息存储提供程序支持 RTF 的文本。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-115">If STORE_RTF_OK is set, the message store provider supports RTF text.</span></span> <span data-ttu-id="ebeb5-116">如果它未设置，消息存储提供程序支持纯文本。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-116">If it is not set, the message store provider supports plain text only.</span></span>
    
## <a name="determine-whether-your-message-store-supports-html"></a><span data-ttu-id="ebeb5-117">确定是否保存邮件支持 HTML</span><span class="sxs-lookup"><span data-stu-id="ebeb5-117">Determine whether your message store supports HTML</span></span>
  
1. <span data-ttu-id="ebeb5-118">调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_STORE_SUPPORT_MASK**属性。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-118">Call the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_STORE_SUPPORT_MASK** property.</span></span> 
    
2. <span data-ttu-id="ebeb5-119">检查 STORE_HTML_OK 位。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-119">Check for the STORE_HTML_OK bit.</span></span> <span data-ttu-id="ebeb5-120">如果设置 STORE_HTML_OK，消息存储提供程序支持的 HTML 文本。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-120">If STORE_HTML_OK is set, the message store provider supports HTML text.</span></span> 
    
## <a name="set-prrtfcompressed"></a><span data-ttu-id="ebeb5-121">设置 PR\_RTF_COMPRESSED</span><span class="sxs-lookup"><span data-stu-id="ebeb5-121">Set PR\_RTF_COMPRESSED</span></span>
  
1. <span data-ttu-id="ebeb5-122">调用消息的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法以打开**PR_RTF_COMPRESSED**属性，指定 IID_IStream 接口标识，并设置 MAPI_CREATE 标志。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-122">Call the message's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_RTF_COMPRESSED** property, specifying IID_IStream as the interface identifier and setting the MAPI_CREATE flag.</span></span> 
    
2. <span data-ttu-id="ebeb5-123">调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数，如果 STORE_UNCOMPRESSED_RTF 位设置中的消息存储**PR_STORE_SUPPORT_MASK**属性传递 STORE_UNCOMPRESSED_RTF 标志。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-123">Call the [WrapCompressedRTFStream](wrapcompressedrtfstream.md) function, passing the STORE_UNCOMPRESSED_RTF flag if the STORE_UNCOMPRESSED_RTF bit is set in the message store's **PR_STORE_SUPPORT_MASK** property.</span></span> 
    
3. <span data-ttu-id="ebeb5-124">通过调用释放原始流其 * * IUnknown::Release * * 方法。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-124">Release the original stream by calling its ** IUnknown::Release ** method.</span></span> 
    
4. <span data-ttu-id="ebeb5-125">调用 * * IStream::Write * * 或从**WrapCompressedRTFStream**返回**IStream::CopyTo** stream 中写入消息文本。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-125">Call either ** IStream::Write ** or **IStream::CopyTo** to write the message text to the stream returned from **WrapCompressedRTFStream**.</span></span>
    
5. <span data-ttu-id="ebeb5-126">对从**OpenProperty**方法返回的流调用的**提交**和**发布**方法。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-126">Call the **Commit** and **Release** methods on the stream returned from the **OpenProperty** method.</span></span> 
    
<span data-ttu-id="ebeb5-127">此时，消息存储提供程序支持 RTF，如果您已完成所有必需的。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-127">At this point, if the message store provider supports RTF, you have done all that is required.</span></span> <span data-ttu-id="ebeb5-128">您可以取决于消息存储提供程序来处理同步消息内容和格式设置并创建**PR\_正文**必要的属性。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-128">You can depend on the message store provider to handle synchronizing the message content and formatting and to create the **PR\_BODY** property if necessary.</span></span> <span data-ttu-id="ebeb5-129">RTF 感知消息存储调用[RTFSync](rtfsync.md)处理同步。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-129">RTF-aware message stores call [RTFSync](rtfsync.md) to handle the synchronization.</span></span> <span data-ttu-id="ebeb5-130">如果在 RTF\_SYNC_BODY_CHANGED 标志设置为 TRUE，则提供程序将重新计算**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-130">If the RTF\_SYNC_BODY_CHANGED flag is set to TRUE, the provider will recompute the **PR_BODY** property.</span></span> 
  
<span data-ttu-id="ebeb5-131">如果您的消息存储提供程序不支持 RTF，您还必须通过设置**PR_BODY**属性添加非 RTF 邮件内容。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-131">If your message store provider does not support RTF, you must also add non-RTF message content by setting the **PR_BODY** property.</span></span> 
  
## <a name="set-prhtml"></a><span data-ttu-id="ebeb5-132">设置 PR_HTML</span><span class="sxs-lookup"><span data-stu-id="ebeb5-132">Set PR_HTML</span></span>
  
1. <span data-ttu-id="ebeb5-133">调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法使用**IStream**接口打开**PR_HTML**属性。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-133">Call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_HTML** property with the **IStream** interface.</span></span> 
    
2. <span data-ttu-id="ebeb5-134">调用**IStream::Write**消息文本数据写入**OpenProperty**从返回的流。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-134">Call **IStream::Write** to write the message text data to the stream returned from **OpenProperty**.</span></span> 
    
3. <span data-ttu-id="ebeb5-135">对要提交的更改并释放其内存流调用**IStream::Commit**和**IUnknown::Release** 。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-135">Call **IStream::Commit** and **IUnknown::Release** on the stream to commit the changes and free its memory.</span></span> 
    
## <a name="set-prbody"></a><span data-ttu-id="ebeb5-136">设置 PR_BODY</span><span class="sxs-lookup"><span data-stu-id="ebeb5-136">Set PR_BODY</span></span>
  
1. <span data-ttu-id="ebeb5-137">调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法使用**IStream**接口打开**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-137">Call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_BODY** property with the **IStream** interface.</span></span> 
    
2. <span data-ttu-id="ebeb5-138">调用**IStream::Write**消息文本数据写入**OpenProperty**从返回的流。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-138">Call **IStream::Write** to write the message text data to the stream returned from **OpenProperty**.</span></span> 
    
3. <span data-ttu-id="ebeb5-139">调用[RTFSync](rtfsync.md)函数以同步带格式的文本。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-139">Call the [RTFSync](rtfsync.md) function to synchronize the text with the formatting.</span></span> <span data-ttu-id="ebeb5-140">由于这是一个新的邮件，设置的 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED 标志指示已更改消息文本的 RTF 和纯文本版本。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-140">Because this is a new message, set both the RTF_SYNC_RTF_CHANGED and RTF_SYNC_BODY_CHANGED flags to indicate that both the RTF and plain text version of the message text has changed.</span></span> <span data-ttu-id="ebeb5-141">**RTFSync**将设置多个相关的属性所需的消息存储提供程序，如**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))，并将它们写到邮件。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-141">**RTFSync** will set several related properties that the message store provider requires, such as **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)), and write them to the message.</span></span>
    
4. <span data-ttu-id="ebeb5-142">对要提交的更改并释放其内存流调用**IStream::Commit**和**IUnknown::Release** 。</span><span class="sxs-lookup"><span data-stu-id="ebeb5-142">Call **IStream::Commit** and **IUnknown::Release** on the stream to commit the changes and free its memory.</span></span> 
    

